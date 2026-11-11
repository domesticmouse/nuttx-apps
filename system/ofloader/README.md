# `system/ofloader`

## Overview
Provides Open flash loader (`system/ofloader`). Enable support for flashloader.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_OFLOADER_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_OFLOADER]
- [Kconfig:CONFIG_SYSTEM_OFLOADER_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_OFLOADER_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_OFLOADER_STACKSIZE]
- [ofloader.h:struct ofloader_msg]
- [ofloader.h:OFLOADER_QNAME]
- [ofloader.h:OFLOADER_WRITE]
- [ofloader.h:OFLOADER_READ]
- [ofloader.h:OFLOADER_VERIFY]
- [ofloader.h:OFLOADER_SYNC]
- [ofloader.h:OFLOADER_ERROR]
- [ofloader.h:OFLOADER_FINSH]
- [ofloader.h:OFLOADER_DEBUG]
- [ofloader.c:struct devinfo_s]
- [ofloader.c:main]
- [segger.c:struct SECTOR_INFO]
- [segger.c:struct FlashDevice]

## Invariants
- [Kconfig:CONFIG_SYSTEM_OFLOADER]: Build and feature compilation gated by `CONFIG_SYSTEM_OFLOADER`.
- [Kconfig:CONFIG_SYSTEM_OFLOADER_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_OFLOADER_PROGNAME`.
- [ofloader.h:CONFIG_SYSTEM_OFLOADER_DEBUG]: Conditional compilation gated by `CONFIG_SYSTEM_OFLOADER_DEBUG`.
- [ofloader.c:CONFIG_BOARDCTL_FINALINIT]: Conditional compilation gated by `CONFIG_BOARDCTL_FINALINIT`.

## Side Effects
- [ofloader.h:syslog]: Writes formatted diagnostic, logging, or console output.
- [ofloader.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [ofloader.c:close]: Performs VFS file or device descriptor I/O operations.
- [ofloader.c:free]: Allocates or releases dynamic heap memory.
- [ofloader.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
