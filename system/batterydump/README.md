# `system/batterydump`

## Overview
Provides Battery dump system tool (`system/batterydump`). Enable the battery dump

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_BATTERYDUMP_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_BATTERYDUMP]
- [Kconfig:CONFIG_SYSTEM_BATTERYDUMP_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_BATTERYDUMP_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_BATTERYDUMP_STACKSIZE]
- [batterydump.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_BATTERYDUMP]: Build and feature compilation gated by `CONFIG_SYSTEM_BATTERYDUMP`.
- [Kconfig:CONFIG_SYSTEM_BATTERYDUMP_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_BATTERYDUMP_PROGNAME`.

## Side Effects
- [batterydump.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [batterydump.c:open]: Performs VFS file or device descriptor I/O operations.
- [batterydump.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
