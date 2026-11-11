# `netutils/esp8266`

## Overview
Provides ESP8266 (`netutils/esp8266`). Enable support for ESP8266 application interface.

## Interface
- [Kconfig:CONFIG_NETUTILS_ESP8266]
- [Kconfig:CONFIG_NETUTILS_ESP8266_DEV_PATH]
- [Kconfig:CONFIG_NETUTILS_ESP8266_BAUDRATE]
- [Kconfig:CONFIG_NETUTILS_ESP8266_MAXTXLEN]
- [esp8266.c:lesp_ans_t]
- [esp8266.c:lesp_socket_t]
- [esp8266.c:lesp_worker_t]
- [esp8266.c:lesp_state_t]
- [esp8266.c:lesp_vsend_cmd]
- [esp8266.c:lesp_read_ans_ok]
- [esp8266.c:lesp_initialize]
- [esp8266.c:lesp_finalize]
- [esp8266.c:lesp_soft_reset]
- [esp8266.c:lesp_ap_connect]
- [esp8266.c:lesp_ap_get]
- [esp8266.c:lesp_get_net]
- [esp8266.c:lesp_set_net]
- [esp8266.c:lesp_set_dhcp]

## Invariants
- [Kconfig:CONFIG_NETUTILS_ESP8266]: Build and feature compilation gated by `CONFIG_NETUTILS_ESP8266`.
- [Kconfig:CONFIG_NETUTILS_ESP8266_DEV_PATH]: Build and feature compilation gated by `CONFIG_NETUTILS_ESP8266_DEV_PATH`.
- [esp8266.c:DEBUGASSERT]: Enforces `DEBUGASSERT(sockfd >= 0)` precondition.
- [esp8266.c:DEBUGASSERT]: Enforces `DEBUGASSERT(((unsigned int)sockfd) < SOCKET_NBR)` precondition.
- [esp8266.c:DEBUGASSERT]: Enforces `DEBUGASSERT(rxlen >= 0)` precondition.
- [esp8266.c:DEBUGASSERT]: Enforces `DEBUGASSERT(rxlen < BUF_WORKER_LEN)` precondition.

## Side Effects
- [esp8266.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [esp8266.c:read]: Performs VFS file or device descriptor I/O operations.
- [esp8266.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
