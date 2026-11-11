# `system/nxrecorder`

## Overview
Provides NxRecorder pcm raw data Recorder (`system/nxrecorder`). Enable support for the NxRecorder pcm raw data recorder library and optional command line interface.

## Interface
- [Makefile:PROGNAME=nxrecorder]
- [Kconfig:CONFIG_SYSTEM_NXRECORDER]
- [Kconfig:CONFIG_NXRECORDER_MAINTHREAD_STACKSIZE]
- [Kconfig:CONFIG_NXRECORDER_RECORDTHREAD_STACKSIZE]
- [Kconfig:CONFIG_NXRECORDER_COMMAND_LINE]
- [nxrecorder.c:struct nxrecorder_ext_fmt_s]
- [nxrecorder.c:nxrecorder_getmp3subformat]
- [nxrecorder.c:nxrecorder_pause]
- [nxrecorder.c:nxrecorder_resume]
- [nxrecorder.c:nxrecorder_setdevice]
- [nxrecorder.c:nxrecorder_stop]
- [nxrecorder.c:nxrecorder_recordinternal]
- [nxrecorder.c:nxrecorder_create]
- [nxrecorder.c:nxrecorder_release]
- [nxrecorder.c:nxrecorder_reference]
- [nxrecorder_amr.c:nxrecorder_write_amr]
- [nxrecorder_common.c:nxrecorder_write_common]
- [nxrecorder_main.c:struct mp_cmd_s]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXRECORDER]: Build and feature compilation gated by `CONFIG_SYSTEM_NXRECORDER`.
- [Kconfig:CONFIG_NXRECORDER_MAINTHREAD_STACKSIZE]: Build and feature compilation gated by `CONFIG_NXRECORDER_MAINTHREAD_STACKSIZE`.
- [Kconfig:depends on AUDIO]: Requires Kconfig dependency condition `AUDIO`.
- [nxrecorder.c:DEBUGASSERT]: Enforces `DEBUGASSERT(errcode > 0)` precondition.
- [nxrecorder.c:DEBUGASSERT]: Enforces `DEBUGASSERT(msg.u.ptr && outstanding > 0)` precondition.
- [nxrecorder.c:DEBUGASSERT]: Enforces `DEBUGASSERT(precorder != NULL)` precondition.

## Side Effects
- [nxrecorder.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [nxrecorder.c:open]: Performs VFS file or device descriptor I/O operations.
- [nxrecorder.c:malloc]: Allocates or releases dynamic heap memory.
- [nxrecorder.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [nxrecorder_amr.c:write]: Performs VFS file or device descriptor I/O operations.
- [nxrecorder_common.c:write]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
