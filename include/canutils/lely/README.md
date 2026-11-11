# `include/canutils/lely`

## Overview
Implements `include/canutils/lely` source and header components (`config.h`) in the NuttX application tree.

## Interface
- [config.h:LELY_NO_ERRNO]
- [config.h:LELY_NO_MALLOC]
- [config.h:LELY_NO_THREADS]
- [config.h:LELY_NO_STDIO]
- [config.h:LELY_NO_ATOMICS]
- [config.h:LELY_HAVE_ITIMERSPEC]
- [config.h:LELY_NO_DAEMON]
- [config.h:LELY_NO_CXX]
- [config.h:LELY_HAVE_SOCKET_CAN]
- [config.h:LELY_NO_CANFD]
- [config.h:LELY_NO_DIAG]
- [config.h:LELY_NO_CO_DCF]
- [config.h:LELY_NO_CO_OBJ_DEFAULT]
- [config.h:LELY_NO_CO_OBJ_FILE]
- [config.h:LELY_NO_CO_OBJ_LIMITS]
- [config.h:LELY_NO_CO_OBJ_NAME]

## Invariants
- [config.h:CONFIG_HAVE_CXX]: Conditional compilation gated by `CONFIG_HAVE_CXX`.
- [config.h:CONFIG_NET_CAN]: Conditional compilation gated by `CONFIG_NET_CAN`.
- [config.h:CONFIG_CANUTILS_LELYCANOPEN_CANFD]: Conditional compilation gated by `CONFIG_CANUTILS_LELYCANOPEN_CANFD`.
- [config.h:CONFIG_CANUTILS_LELYCANOPEN_DIAG]: Conditional compilation gated by `CONFIG_CANUTILS_LELYCANOPEN_DIAG`.
- [config.h:CONFIG_CANUTILS_LELYCANOPEN_DCF]: Conditional compilation gated by `CONFIG_CANUTILS_LELYCANOPEN_DCF`.
- [config.h:CONFIG_CANUTILS_LELYCANOPEN_OBJDEFAULT]: Conditional compilation gated by `CONFIG_CANUTILS_LELYCANOPEN_OBJDEFAULT`.

## Side Effects
- None

## Verification
- Run: `make test`
