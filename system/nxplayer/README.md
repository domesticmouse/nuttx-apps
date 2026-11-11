# `system/nxplayer`

## Overview
Provides NxPlayer Media Player (`system/nxplayer`). Enable support for the NxPlayer media player library and optional command line interface.

## Interface
- [Makefile:PROGNAME=nxplayer]
- [Kconfig:CONFIG_SYSTEM_NXPLAYER]
- [Kconfig:CONFIG_NXPLAYER_MAINTHREAD_STACKSIZE]
- [Kconfig:CONFIG_NXPLAYER_PLAYTHREAD_STACKSIZE]
- [Kconfig:CONFIG_NXPLAYER_COMMAND_LINE]
- [nxplayer.c:struct nxplayer_ext_fmt_s]
- [nxplayer.c:nxplayer_getmidisubformat]
- [nxplayer.c:nxplayer_getmp3subformat]
- [nxplayer.c:nxplayer_getsbcsubformat]
- [nxplayer.c:nxplayer_setvolume]
- [nxplayer.c:nxplayer_setequalization]
- [nxplayer.c:nxplayer_setbass]
- [nxplayer.c:nxplayer_settreble]
- [nxplayer.c:nxplayer_setbalance]
- [nxplayer.c:nxplayer_pause]
- [nxplayer.c:nxplayer_resume]
- [nxplayer.c:nxplayer_fforward]
- [nxplayer.c:nxplayer_rewind]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXPLAYER]: Build and feature compilation gated by `CONFIG_SYSTEM_NXPLAYER`.
- [Kconfig:CONFIG_NXPLAYER_MAINTHREAD_STACKSIZE]: Build and feature compilation gated by `CONFIG_NXPLAYER_MAINTHREAD_STACKSIZE`.
- [Kconfig:depends on AUDIO]: Requires Kconfig dependency condition `AUDIO`.
- [Kconfig:depends on NET_IPv4 && NET_TCP]: Requires Kconfig dependency condition `NET_IPv4 && NET_TCP`.
- [nxplayer.c:DEBUGASSERT]: Enforces `DEBUGASSERT(s != -1)` precondition.
- [nxplayer.c:DEBUGASSERT]: Enforces `DEBUGASSERT(errcode > 0)` precondition.

## Side Effects
- [nxplayer.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [nxplayer.c:open]: Performs VFS file or device descriptor I/O operations.
- [nxplayer.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [nxplayer.c:malloc]: Allocates or releases dynamic heap memory.
- [nxplayer.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [nxplayer.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
