# `netutils/libwebsockets`

## Overview
Provides libwebsockets library (current version) (`netutils/libwebsockets`). Enables the libwebsockets library.

## Interface
- [Kconfig:CONFIG_NETUTILS_LIBWEBSOCKETS]
- [Kconfig:CONFIG_NETUTILS_LIBWEBSOCKETS_VERSION]
- [Kconfig:CONFIG_NETUTILS_LIBWEBSOCKETS_SERVER]
- [Kconfig:CONFIG_NETUTILS_LIBWEBSOCKETS_TLS]
- [lws_config.h:LWS_LIBRARY_VERSION_NUMBER]
- [lws_config.h:LWS_MAX_SMP]
- [lws_config.h:LWS_BUILD_HASH]
- [lws_config.h:LWS_CLIENT_HTTP_PROXYING]
- [lws_config.h:LWS_HAS_INTPTR_T]
- [lws_config.h:LWS_HAS_GETOPT_LONG]
- [lws_config.h:LWS_HAVE_ATOLL]
- [lws_config.h:LWS_HAVE_CLOCK_GETTIME]
- [lws_config.h:LWS_HAVE_LOCALTIME_R]
- [lws_config.h:LWS_HAVE_GMTIME_R]
- [lws_config.h:LWS_HAVE_CTIME_R]
- [lws_config.h:LWS_HAVE_GETGRGID_R]

## Invariants
- [Kconfig:CONFIG_NETUTILS_LIBWEBSOCKETS]: Build and feature compilation gated by `CONFIG_NETUTILS_LIBWEBSOCKETS`.
- [Kconfig:CONFIG_NETUTILS_LIBWEBSOCKETS_VERSION]: Build and feature compilation gated by `CONFIG_NETUTILS_LIBWEBSOCKETS_VERSION`.
- [Kconfig:depends on NET]: Requires Kconfig dependency condition `NET`.
- [Kconfig:depends on OPENSSL_MBEDTLS_WRAPPER]: Requires Kconfig dependency condition `OPENSSL_MBEDTLS_WRAPPER`.
- [lws_config.h:CONFIG_NETUTILS_LIBWEBSOCKETS_TLS]: Conditional compilation gated by `CONFIG_NETUTILS_LIBWEBSOCKETS_TLS`.
- [lws_config.h:CONFIG_PIPES]: Conditional compilation gated by `CONFIG_PIPES`.

## Side Effects
- None

## Verification
- Run: `make test`
