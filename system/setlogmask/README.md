# `system/setlogmask`

## Overview
Provides 'setlogmask' command (`system/setlogmask`). Enable support for 'setlogmask' command used to set syslog level.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_SETLOGMASK_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_SETLOGMASK]
- [Kconfig:CONFIG_SYSTEM_SETLOGMASK_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_SETLOGMASK_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_SETLOGMASK_STACKSIZE]
- [setlogmask.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_SETLOGMASK]: Build and feature compilation gated by `CONFIG_SYSTEM_SETLOGMASK`.
- [Kconfig:CONFIG_SYSTEM_SETLOGMASK_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_SETLOGMASK_PROGNAME`.
- [setlogmask.c:CONFIG_SYSLOG_IOCTL]: Conditional compilation gated by `CONFIG_SYSLOG_IOCTL`.

## Side Effects
- [setlogmask.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [setlogmask.c:open]: Performs VFS file or device descriptor I/O operations.
- [setlogmask.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
