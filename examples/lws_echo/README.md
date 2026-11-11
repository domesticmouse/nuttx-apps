# lws_echo

## Overview
libwebsockets WebSocket echo server (`lws_echo`). Simple WebSocket echo server using libwebsockets without TLS.

## Interface
- `[Kconfig:EXAMPLES_LWS_ECHO]` - Build configuration option `EXAMPLES_LWS_ECHO`
- `[Kconfig:EXAMPLES_LWS_ECHO_PROGNAME]` - Build configuration option `EXAMPLES_LWS_ECHO_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LWS_ECHO_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_LWS_ECHO_PROGNAME}`
- `[lws_echo_main.c:struct lws_echo_session_s]` - Structure definition `lws_echo_session_s`
- `[lws_echo_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NETUTILS_LIBWEBSOCKETS && NETUTILS_LIBWEBSOCKETS_SERVER]` - Requires kernel/app configuration `NETUTILS_LIBWEBSOCKETS && NETUTILS_LIBWEBSOCKETS_SERVER`
- `[lws_echo_main.c:CONFIG_EXAMPLES_LWS_ECHO_PORT]` - Configuration guard on `CONFIG_EXAMPLES_LWS_ECHO_PORT`

## Side Effects
- `[lws_echo_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
