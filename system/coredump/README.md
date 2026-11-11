# `system/coredump`

## Overview
Provides Coredump tool capture system status (`system/coredump`). This is the stack size that will be used when starting the coredump.

## Interface
- [Makefile:PROGNAME=coredump]
- [Kconfig:CONFIG_SYSTEM_COREDUMP]
- [Kconfig:CONFIG_SYSTEM_COREDUMP_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_COREDUMP_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_COREDUMP_SWAPBUFFER_SIZE]
- [coredump.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_COREDUMP]: Build and feature compilation gated by `CONFIG_SYSTEM_COREDUMP`.
- [Kconfig:CONFIG_SYSTEM_COREDUMP_STACKSIZE]: Build and feature compilation gated by `CONFIG_SYSTEM_COREDUMP_STACKSIZE`.
- [Kconfig:depends on COREDUMP]: Requires Kconfig dependency condition `COREDUMP`.
- [Kconfig:depends on SYSTEM_COREDUMP_RESTORE]: Requires Kconfig dependency condition `SYSTEM_COREDUMP_RESTORE`.
- [coredump.c:CONFIG_BOARD_COREDUMP_COMPRESSION]: Conditional compilation gated by `CONFIG_BOARD_COREDUMP_COMPRESSION`.
- [coredump.c:CONFIG_BOARD_MEMORY_RANGE]: Conditional compilation gated by `CONFIG_BOARD_MEMORY_RANGE`.

## Side Effects
- [coredump.c:mkdir]: Performs VFS file or device descriptor I/O operations.
- [coredump.c:malloc]: Allocates or releases dynamic heap memory.
- [coredump.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
