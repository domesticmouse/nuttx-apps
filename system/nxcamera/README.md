# `system/nxcamera`

## Overview
Provides NxCamera video test application (`system/nxcamera`). Enable support for the NxCam media tester library and optional command line interface.

## Interface
- [Makefile:PROGNAME=nxcamera]
- [Kconfig:CONFIG_SYSTEM_NXCAMERA]
- [Kconfig:CONFIG_NXCAMERA_MAINTHREAD_STACKSIZE]
- [Kconfig:CONFIG_NXCAMERA_LOOPTHREAD_STACKSIZE]
- [Kconfig:CONFIG_NXCAMERA_MSG_PRIO]
- [nxcamera.c:nxcamera_setdevice]
- [nxcamera.c:nxcamera_setfb]
- [nxcamera.c:nxcamera_setfile]
- [nxcamera.c:nxcamera_stop]
- [nxcamera.c:nxcamera_stream]
- [nxcamera.c:nxcamera_ioctl]
- [nxcamera.c:nxcamera_create]
- [nxcamera.c:nxcamera_release]
- [nxcamera.c:nxcamera_reference]
- [nxcamera_main.c:struct nxcamera_cmd_s]
- [nxcamera_main.c:struct nxcamera_ctrl_name_s]
- [nxcamera_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXCAMERA]: Build and feature compilation gated by `CONFIG_SYSTEM_NXCAMERA`.
- [Kconfig:CONFIG_NXCAMERA_MAINTHREAD_STACKSIZE]: Build and feature compilation gated by `CONFIG_NXCAMERA_MAINTHREAD_STACKSIZE`.
- [Kconfig:depends on VIDEO]: Requires Kconfig dependency condition `VIDEO`.
- [nxcamera.c:DEBUGASSERT]: Enforces `DEBUGASSERT(errcode > 0)` precondition.
- [nxcamera.c:DEBUGASSERT]: Enforces `DEBUGASSERT(pcam != NULL)` precondition.
- [nxcamera.c:DEBUGASSERT]: Enforces `DEBUGASSERT(device != NULL)` precondition.

## Side Effects
- [nxcamera.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [nxcamera.c:open]: Performs VFS file or device descriptor I/O operations.
- [nxcamera.c:free]: Allocates or releases dynamic heap memory.
- [nxcamera.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [nxcamera_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
