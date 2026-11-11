# `crypto/mbedtls/include`

## Overview
Implements `crypto/mbedtls/include` source and header components (`aes_alt.h`, `cmac_alt.h`, `dev_alt.h`, `md5_alt.h` and 5 more files) in the NuttX application tree.

## Interface
- [aes_alt.h:struct mbedtls_aes_context]
- [aes_alt.h:mbedtls_aes_context]
- [aes_alt.h:MAX_KEY_SIZE]
- [cmac_alt.h:struct mbedtls_cmac_context_t]
- [cmac_alt.h:CMAC_KEY_MAX_SIZE]
- [dev_alt.h:struct cryptodev_context_s]
- [dev_alt.h:cryptodev_context_t]
- [dev_alt.h:cryptodev_init]
- [dev_alt.h:cryptodev_clone]
- [dev_alt.h:cryptodev_free]
- [dev_alt.h:cryptodev_get_session]
- [dev_alt.h:cryptodev_free_session]
- [dev_alt.h:cryptodev_crypt]
- `mbedtls`: [./mbedtls/README.md](./mbedtls/README.md) - Implements `crypto/mbedtls/include/mbedtls` source and header components (`mbedtls_config.h`) in the NuttX application tree.

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
