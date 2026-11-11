# Password File & Authentication Library (`fsutils/passwd`)

## Overview
Implements user account management and password verification (`CONFIG_FSUTILS_PASSWD`) backed by an `/etc/passwd`-style flat file using PBKDF2-HMAC-SHA256 modular crypt hashes (`$pbkdf2-sha256$...`) and semaphore-synchronized updates.

## Interface
- `[passwd_verify.c:passwd_verify]`: Verifies a plaintext password against a user's stored record in `CONFIG_FSUTILS_PASSWD_PATH`.
- `[passwd_find.c:passwd_find]`: Searches the password file for a username and populates `struct passwd_s`.
- `[passwd_encrypt.c:passwd_encrypt]` / `[passwd_pbkdf2.c:passwd_pbkdf2_hmac_sha256]`: Enforces password complexity rules, generates random salt, and derives PBKDF2-HMAC-SHA256 hashes.
- `[passwd_adduser.c:passwd_adduser]` / `[passwd_deluser.c:passwd_deluser]` / `[passwd_update.c:passwd_update]`: High-level user creation, deletion, and password update APIs.
- `[passwd_append.c:passwd_append]` / `[passwd_delete.c:passwd_delete]`: Low-level password file record append and atomic rewrite helpers.
- `[passwd_lock.c:passwd_lock]` / `[passwd_lock.c:passwd_unlock]`: Acquires and releases the password file synchronization semaphore.
- `[passwd.h:passwd_s]`, `[passwd.h:PASSWD_MCF_PREFIX]`, `[passwd.h:PASSWD_SALT_BYTES]`, `[passwd.h:PASSWD_HASH_BYTES]`, `[passwd.h:MAX_ENCRYPTED]`: Record structure and format constants.
- `[Kconfig:FSUTILS_PASSWD]`, `[Kconfig:FSUTILS_PASSWD_PATH]`, `[Kconfig:FSUTILS_PASSWD_READONLY]`, `[Kconfig:FSUTILS_PASSWD_PBKDF2_ITERATIONS]`: Build and security parameter flags.

## Invariants
- `[passwd_encrypt.c:validate_password_complexity]`: New passwords must be `8..256` characters and contain at least one uppercase letter, one lowercase letter, one digit, and one special character from `!@#$%^&*()_+-=[]{}|;:,.<>?`.
- `[passwd_verify.c:passwd_verify_hash]`: Stored hashes must follow `$pbkdf2-sha256$<iter>$<salt>$<hash>` with `iterations` in `1..200000`, non-empty base64url salt, and a 32-byte decoded digest.
- `[passwd_pbkdf2.c:passwd_pbkdf2_hmac_sha256]`: Requires non-NULL `pass`, `salt`, and `out` pointers and non-zero `passlen`, `saltlen`, `iterations`, and `outlen`.
- `[passwd_find.c:passwd_find]` and `[passwd_encrypt.c:passwd_encrypt]`: Encrypted password strings must be `< MAX_ENCRYPTED` (`96` bytes).
- `[passwd_adduser.c:passwd_adduser]`: Fails with `-EEXIST` if the username already exists in the password file.

## Side Effects
- `[passwd_lock.c:passwd_lock]` and `[passwd_lock.c:passwd_unlock]`: Acquire and release the named semaphore `"pwsem"` (when `CONFIG_FS_NAMED_SEMAPHORES` is enabled) or process semaphore `g_passwd_sem`.
- `[passwd_pbkdf2.c:passwd_pbkdf2_hmac_sha256]`: Opens `/dev/crypto` and issues `CRIOGET`, `CIOCGSESSION`, `CIOCCRYPT`, and `CIOCFSESSION` `ioctl` calls for HMAC-SHA256 derivation.
- `[passwd_encrypt.c:passwd_fill_random]`: Reads cryptographic random bytes via `getrandom()` or `/dev/urandom`.
- `[passwd_append.c:passwd_append]` and `[passwd_delete.c:passwd_delete]`: Read, append to, rewrite via temporary `.tmp` file, `unlink`, and `rename` `CONFIG_FSUTILS_PASSWD_PATH`.

## Verification
- Run: `make test`
