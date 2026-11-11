# `crypto`

## Overview
Groups Cryptography Library Support (`crypto`) components and utilities for NuttX.

## Subdirectories & Boundaries
- `controlse`: [./controlse/README.md](./controlse/README.md) - NXP SE05x Secure Element keystore management library and CLI tool (`controlse`) providing key generation, ECDSA signing/verification, X.509 certificate/CSR handling, and Mbed TLS PK integration.
- `mbedtls`: [./mbedtls/README.md](./mbedtls/README.md) - Provides Mbed TLS Cryptography Library (`crypto/mbedtls`). Enable support for Mbed TLS.
- `openssl_mbedtls_wrapper`: [./openssl_mbedtls_wrapper/README.md](./openssl_mbedtls_wrapper/README.md) - Implements openssl mbedtls wrapper (`crypto/openssl_mbedtls_wrapper`) for the NuttX application subsystem.
- `wolfssl`: [./wolfssl/README.md](./wolfssl/README.md) - Provides wolfSSL SSL/TLS Cryptography Library (`crypto/wolfssl`). Enable support for wolfSSL
