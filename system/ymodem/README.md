# `system/ymodem`

## Overview
Provides YMODEM (`system/ymodem`). Enable support for ymodem.

## Interface
- [Makefile:PROGNAME=sb]
- [Kconfig:CONFIG_SYSTEM_YMODEM]
- [Kconfig:CONFIG_SYSTEM_YMODEM_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_YMODEM_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_YMODEM_DEBUG]
- [ymodem.h:struct ymodem_ctx_s]
- [ymodem.h:ymodem_recv]
- [ymodem.h:ymodem_send]
- [ymodem.h:YMODEM_PACKET_SIZE]
- [ymodem.h:YMODEM_PACKET_1K_SIZE]
- [ymodem.h:YMODEM_FILENAME_PACKET]
- [ymodem.h:YMODEM_DATA_PACKET]
- [rb_main.c:struct ymodem_priv_s]
- [rb_main.c:main]
- [sb_main.c:struct ymodem_priv_s]
- [sb_main.c:main]
- [sbrb.py:format_time]
- [sbrb.py:ymodem_stdread]

## Invariants
- [Kconfig:CONFIG_SYSTEM_YMODEM]: Build and feature compilation gated by `CONFIG_SYSTEM_YMODEM`.
- [Kconfig:CONFIG_SYSTEM_YMODEM_STACKSIZE]: Build and feature compilation gated by `CONFIG_SYSTEM_YMODEM_STACKSIZE`.
- [Kconfig:depends on SYSTEM_YMODEM_DEBUG]: Requires Kconfig dependency condition `SYSTEM_YMODEM_DEBUG`.
- [ymodem.h:CONFIG_SYSTEM_YMODEM_DEBUG_FILEPATH]: Conditional compilation gated by `CONFIG_SYSTEM_YMODEM_DEBUG_FILEPATH`.
- [rb_main.c:pthread_mutex_lock]: Synchronizes concurrent access across threads or critical sections.
- [rb_main.c:pthread_mutex_unlock]: Synchronizes concurrent access across threads or critical sections.

## Side Effects
- [rb_main.c:write]: Performs VFS file or device descriptor I/O operations.
- [rb_main.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [rb_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [sb_main.c:read]: Performs VFS file or device descriptor I/O operations.
- [sb_main.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [sb_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
