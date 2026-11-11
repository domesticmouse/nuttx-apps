# `crypto/wolfssl`

## Overview
Provides wolfSSL SSL/TLS Cryptography Library (`crypto/wolfssl`). Enable support for wolfSSL

## Interface
- [Makefile:PROGNAME=$(CONFIG_WOLFCRYPT_APP_BENCHMARK_PROGNAME)]
- [Makefile:PROGNAME=$(CONFIG_WOLFCRYPT_APP_SELFTEST_PROGNAME)]
- [Makefile:PROGNAME=$(CONFIG_WOLFSSL_APP_CLIENT_SERVER_PROGNAME)]
- [Kconfig:CONFIG_CRYPTO_WOLFSSL]
- [Kconfig:CONFIG_WOLFSSL_VERSION]
- [Kconfig:CONFIG_WOLFCRYPT_APPS]
- [Kconfig:CONFIG_WOLFSSL_DEFAULT_TASK_STACKSIZE]
- [user_settings.h:SINGLE_THREADED]
- [user_settings.h:WOLFSSL_SMALL_STACK]
- [user_settings.h:NO_FILESYSTEM]
- [user_settings.h:WOLF_C99]
- [user_settings.h:WOLFSSL_SP_MATH_ALL]
- [user_settings.h:HAVE_ECC]
- [user_settings.h:ECC_TIMING_RESISTANT]
- [user_settings.h:WC_RSA_BLINDING]
- [user_settings.h:NO_MD4]

## Invariants
- [Kconfig:CONFIG_CRYPTO_WOLFSSL]: Build and feature compilation gated by `CONFIG_CRYPTO_WOLFSSL`.
- [Kconfig:CONFIG_WOLFSSL_VERSION]: Build and feature compilation gated by `CONFIG_WOLFSSL_VERSION`.
- [Kconfig:depends on ALLOW_GPL_COMPONENTS]: Requires Kconfig dependency condition `ALLOW_GPL_COMPONENTS`.

## Side Effects
- None

## Verification
- Run: `make test`
