# `crypto/openssl_mbedtls_wrapper/mbedtls`

## Overview
Implements `crypto/openssl_mbedtls_wrapper/mbedtls` source and header components (`aes.c`, `asn1.c`, `bio_b64.c`, `bio_lib.c` and 34 more files) in the NuttX application tree.

## Interface
- [ssl_methods.h:X509_method]
- [ssl_methods.h:EVP_PKEY_method]
- [ssl_methods.h:IMPLEMENT_TLS_METHOD_FUNC]
- [ssl_methods.h:IMPLEMENT_TLS_METHOD]
- [ssl_methods.h:IMPLEMENT_SSL_METHOD]
- [ssl_methods.h:IMPLEMENT_X509_METHOD]
- [ssl_methods.h:IMPLEMENT_PKEY_METHOD]
- [ssl_pm.h:ssl_pm_new]
- [ssl_pm.h:ssl_pm_free]
- [ssl_pm.h:ssl_pm_handshake]
- [ssl_pm.h:ssl_pm_shutdown]
- [ssl_pm.h:ssl_pm_clear]
- [ssl_pm.h:ssl_pm_read]
- [ssl_pm.h:ssl_pm_send]
- [ssl_pm.h:ssl_pm_pending]
- [ssl_pm.h:ssl_pm_set_fd]
- [ssl_pm.h:ssl_pm_get_fd]
- [ssl_pm.h:ssl_pm_get_state]

## Invariants
- [ssl_cert.c:assert]: Enforces `assert(ctx)` precondition.
- [stack.c:CONFIG_MIN_NODES]: Conditional compilation gated by `CONFIG_MIN_NODES`.

## Side Effects
- [aes.c:malloc]: Allocates or releases dynamic heap memory.
- [bio_lib.c:zalloc]: Allocates or releases dynamic heap memory.
- [bss_mem.c:realloc]: Allocates or releases dynamic heap memory.
- [digest.c:malloc]: Allocates or releases dynamic heap memory.
- [hmac.c:malloc]: Allocates or releases dynamic heap memory.
- [ssl_pm.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
