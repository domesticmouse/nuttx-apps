# `system/nxlooper`

## Overview
Provides NxLooper audio test application (`system/nxlooper`). Enable support for the NxLoop media tester library and optional command line interface.

## Interface
- [Makefile:PROGNAME=nxlooper]
- [Kconfig:CONFIG_SYSTEM_NXLOOPER]
- [Kconfig:CONFIG_NXLOOPER_MAINTHREAD_STACKSIZE]
- [Kconfig:CONFIG_NXLOOPER_LOOPTHREAD_STACKSIZE]
- [Kconfig:CONFIG_NXLOOPER_MSG_PRIO]
- [nxlooper.c:nxlooper_setvolume]
- [nxlooper.c:nxlooper_pause]
- [nxlooper.c:nxlooper_resume]
- [nxlooper.c:nxlooper_setdevice]
- [nxlooper.c:nxlooper_stop]
- [nxlooper.c:nxlooper_loopback]
- [nxlooper.c:nxlooper_create]
- [nxlooper.c:nxlooper_release]
- [nxlooper.c:nxlooper_reference]
- [nxlooper.c:nxlooper_systemreset]
- [nxlooper_main.c:struct mp_cmd_s]
- [nxlooper_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXLOOPER]: Build and feature compilation gated by `CONFIG_SYSTEM_NXLOOPER`.
- [Kconfig:CONFIG_NXLOOPER_MAINTHREAD_STACKSIZE]: Build and feature compilation gated by `CONFIG_NXLOOPER_MAINTHREAD_STACKSIZE`.
- [Kconfig:depends on AUDIO]: Requires Kconfig dependency condition `AUDIO`.
- [nxlooper.c:DEBUGASSERT]: Enforces `DEBUGASSERT(errcode > 0)` precondition.
- [nxlooper.c:DEBUGASSERT]: Enforces `DEBUGASSERT(plooper != NULL)` precondition.
- [nxlooper.c:DEBUGASSERT]: Enforces `DEBUGASSERT(pdevice != NULL)` precondition.

## Side Effects
- [nxlooper.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [nxlooper.c:open]: Performs VFS file or device descriptor I/O operations.
- [nxlooper.c:calloc]: Allocates or releases dynamic heap memory.
- [nxlooper.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [nxlooper_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
