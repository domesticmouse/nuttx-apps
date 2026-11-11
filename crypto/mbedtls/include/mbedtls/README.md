# `crypto/mbedtls/include/mbedtls`

## Overview
Implements `crypto/mbedtls/include/mbedtls` source and header components (`mbedtls_config.h`) in the NuttX application tree.

## Interface
- [mbedtls_config.h:MBEDTLS_HAVE_ASM]
- [mbedtls_config.h:MBEDTLS_HAVE_TIME]
- [mbedtls_config.h:MBEDTLS_HAVE_TIME_DATE]
- [mbedtls_config.h:MBEDTLS_PLATFORM_MEMORY]
- [mbedtls_config.h:MBEDTLS_AES_ALT]
- [mbedtls_config.h:MBEDTLS_CMAC_ALT]
- [mbedtls_config.h:MBEDTLS_MD5_ALT]
- [mbedtls_config.h:MBEDTLS_POLY1305_ALT]
- [mbedtls_config.h:MBEDTLS_RIPEMD160_ALT]
- [mbedtls_config.h:MBEDTLS_SHA1_ALT]
- [mbedtls_config.h:MBEDTLS_SHA256_ALT]
- [mbedtls_config.h:MBEDTLS_SHA512_ALT]
- [mbedtls_config.h:MBEDTLS_BIGNUM_ALT]
- [mbedtls_config.h:MBEDTLS_ENTROPY_HARDWARE_ALT]
- [mbedtls_config.h:MBEDTLS_AES_ROM_TABLES]
- [mbedtls_config.h:MBEDTLS_AES_FEWER_TABLES]

## Invariants
- [mbedtls_config.h:CONFIG_MBEDTLS_HAVE_ASM]: Conditional compilation gated by `CONFIG_MBEDTLS_HAVE_ASM`.
- [mbedtls_config.h:CONFIG_MBEDTLS_HAVE_TIME]: Conditional compilation gated by `CONFIG_MBEDTLS_HAVE_TIME`.
- [mbedtls_config.h:CONFIG_MBEDTLS_HAVE_TIME_DATE]: Conditional compilation gated by `CONFIG_MBEDTLS_HAVE_TIME_DATE`.
- [mbedtls_config.h:CONFIG_MBEDTLS_PLATFORM_MEMORY]: Conditional compilation gated by `CONFIG_MBEDTLS_PLATFORM_MEMORY`.
- [mbedtls_config.h:CONFIG_MBEDTLS_AES_ALT]: Conditional compilation gated by `CONFIG_MBEDTLS_AES_ALT`.
- [mbedtls_config.h:CONFIG_MBEDTLS_CMAC_ALT]: Conditional compilation gated by `CONFIG_MBEDTLS_CMAC_ALT`.

## Side Effects
- None

## Verification
- Run: `make test`
