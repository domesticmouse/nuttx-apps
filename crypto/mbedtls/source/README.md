# `crypto/mbedtls/source`

## Overview
Implements `crypto/mbedtls/source` source and header components (`aes_alt.c`, `bignum_alt.c`, `cmac_alt.c`, `dev_alt.c` and 7 more files) in the NuttX application tree.

## Interface
- [aes_alt.c:mbedtls_aes_init]
- [aes_alt.c:mbedtls_aes_free]
- [aes_alt.c:mbedtls_aes_setkey_enc]
- [aes_alt.c:mbedtls_aes_setkey_dec]
- [aes_alt.c:mbedtls_aes_crypt_ecb]
- [aes_alt.c:mbedtls_aes_crypt_cbc]
- [aes_alt.c:mbedtls_aes_crypt_ctr]
- [aes_alt.c:mbedtls_aes_xts_init]
- [aes_alt.c:mbedtls_aes_xts_free]
- [aes_alt.c:mbedtls_aes_xts_setkey_enc]
- [aes_alt.c:mbedtls_aes_xts_setkey_dec]
- [aes_alt.c:mbedtls_aes_crypt_xts]
- [aes_alt.c:mbedtls_aes_crypt_cfb128]
- [aes_alt.c:mbedtls_aes_crypt_cfb8]
- [aes_alt.c:mbedtls_aes_crypt_ofb]
- [bignum_alt.c:mbedtls_mpi_add_mpi]
- [bignum_alt.c:mbedtls_mpi_sub_mpi]
- [bignum_alt.c:mbedtls_mpi_mul_mpi]

## Invariants
- [entropy_alt.c:CONFIG_MBEDTLS_ENTROPY_HARDWARE_ALT]: Conditional compilation gated by `CONFIG_MBEDTLS_ENTROPY_HARDWARE_ALT`.
- [entropy_alt.c:CONFIG_MBEDTLS_PSA_CRYPTO_EXTERNAL_RNG]: Conditional compilation gated by `CONFIG_MBEDTLS_PSA_CRYPTO_EXTERNAL_RNG`.

## Side Effects
- [bignum_alt.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [bignum_alt.c:open]: Performs VFS file or device descriptor I/O operations.
- [dev_alt.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [dev_alt.c:open]: Performs VFS file or device descriptor I/O operations.
- [entropy_alt.c:open]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
