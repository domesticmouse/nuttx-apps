# `netutils/cmux`

## Overview
Provides Cmux tool (`netutils/cmux`). Enable the CMUX (GSM 07.10) multiplexing protocol utility. CMUX allows multiplexing multiple virtual serial connections

## Interface
- [Kconfig:CONFIG_NETUTILS_CMUX]
- [cmux.h:struct cmux_parse_s]
- [cmux.h:struct cmux_stream_buffer_s]
- [cmux.h:struct cmux_channel_s]
- [cmux.h:CMUX_BIT0]
- [cmux.h:CMUX_BIT1]
- [cmux.h:CMUX_BIT2]
- [cmux.h:CMUX_BIT3]
- [cmux.h:CMUX_BIT4]
- [cmux.h:CMUX_BIT5]
- [cmux.h:CMUX_BIT6]
- [cmux.h:CMUX_BIT7]
- [cmux.h:CMUX_BUFFER_SZ]
- [cmux.h:CMUX_CHANNEL_NAME_SZ]
- [cmux.h:CMUX_FRAME_MAX_SIZE]
- [cmux.h:CMUX_OPEN_FLAG]
- [cmux.c:struct cmux_ctl_s]
- [cmux.c:cmux_create]

## Invariants
- [Kconfig:CONFIG_NETUTILS_CMUX]: Build and feature compilation gated by `CONFIG_NETUTILS_CMUX`.

## Side Effects
- [cmux.c:write]: Performs VFS file or device descriptor I/O operations.
- [cmux.c:malloc]: Allocates or releases dynamic heap memory.
- [cmux.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
