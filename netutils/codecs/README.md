# `netutils/codecs`

## Overview
Provides CODEC Library (`netutils/codecs`). Enables the netutils/code library: Base64 coding, URL coding, MD5.

## Interface
- [Kconfig:CONFIG_NETUTILS_CODECS]
- [Kconfig:CONFIG_CODECS_BASE64]
- [Kconfig:CONFIG_CODECS_HASH_MD5]
- [Kconfig:CONFIG_CODECS_URLCODE]
- [base64.c:base64_encode_length]
- [base64.c:base64_encode]
- [base64.c:base64_decode_length]
- [base64.c:base64_decode]
- [base64.c:base64w_encode]
- [base64.c:base64w_decode]
- [base64.c:base64url_encode]
- [base64.c:base64url_decode]
- [md5.c:md5_init]
- [md5.c:md5_update]
- [md5.c:md5_final]
- [md5.c:md5_transform]
- [md5.c:md5_sum]
- [md5.c:md5_hash]

## Invariants
- [Kconfig:CONFIG_NETUTILS_CODECS]: Build and feature compilation gated by `CONFIG_NETUTILS_CODECS`.
- [Kconfig:CONFIG_CODECS_BASE64]: Build and feature compilation gated by `CONFIG_CODECS_BASE64`.
- [base64.c:CONFIG_CODECS_BASE64]: Conditional compilation gated by `CONFIG_CODECS_BASE64`.
- [md5.c:CONFIG_CODECS_HASH_MD5]: Conditional compilation gated by `CONFIG_CODECS_HASH_MD5`.
- [md5.c:CONFIG_ENDIAN_BIG]: Conditional compilation gated by `CONFIG_ENDIAN_BIG`.
- [urldecode.c:CONFIG_CODECS_URLCODE]: Conditional compilation gated by `CONFIG_CODECS_URLCODE`.

## Side Effects
- [base64.c:malloc]: Allocates or releases dynamic heap memory.
- [md5.c:open]: Performs VFS file or device descriptor I/O operations.
- [md5.c:malloc]: Allocates or releases dynamic heap memory.
- [urldecode.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
