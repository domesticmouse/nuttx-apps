# `netutils/libcoap`

## Overview
Provides LIBCOAP (`netutils/libcoap`). libcoap is a C implementation of a lightweight application-protocol for devices that are constrained their resources such as computing

## Interface
- [Makefile:PROGNAME=coap_server]
- [Kconfig:CONFIG_NETUTILS_LIBCOAP]
- [Kconfig:CONFIG_LIBCOAP_VERSION]
- [Kconfig:CONFIG_NETUTILS_LIBCOAP_EXAMPLE]
- [Kconfig:CONFIG_NETUTILS_LIBCOAP_EXAMPLE_PRIORITY]
- [coap_config.h:COAP_CLIENT_SUPPORT]
- [coap_config.h:COAP_SERVER_SUPPORT]
- [coap_config.h:COAP_WITH_OBSERVE_PERSIST]
- [coap_config.h:COAP_OSCORE_SUPPORT]
- [coap_config.h:COAP_ASYNC_SUPPORT]
- [coap_config.h:COAP_DISABLE_TCP]
- [coap_config.h:COAP_IPV4_SUPPORT]
- [coap_config.h:COAP_IPV6_SUPPORT]
- [coap_config.h:COAP_AF_UNIX_SUPPORT]
- [coap_config.h:COAP_Q_BLOCK_SUPPORT]
- [coap_config.h:HAVE_GETADDRINFO]

## Invariants
- [Kconfig:CONFIG_NETUTILS_LIBCOAP]: Build and feature compilation gated by `CONFIG_NETUTILS_LIBCOAP`.
- [Kconfig:CONFIG_LIBCOAP_VERSION]: Build and feature compilation gated by `CONFIG_LIBCOAP_VERSION`.
- [coap_config.h:CONFIG_LIBCOAP_EXAMPLE_CLIENT]: Conditional compilation gated by `CONFIG_LIBCOAP_EXAMPLE_CLIENT`.

## Side Effects
- None

## Verification
- Run: `make test`
