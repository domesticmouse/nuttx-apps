# `system/trace`

## Overview
Provides Trace command (`system/trace`). Enable support for the trace command.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_TRACE_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_TRACE]
- [Kconfig:CONFIG_SYSTEM_TRACE_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_TRACE_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_TRACE_STACKSIZE]
- [trace.h:trace_dump]
- [trace.h:trace_dump_clear]
- [trace.h:trace_dump_get_overwrite]
- [trace.h:trace_dump_set_overwrite]
- [trace.c:main]
- [trace_dump.c:trace_dump]
- [trace_dump.c:trace_dump_clear]
- [trace_dump.c:trace_dump_get_overwrite]
- [trace_dump.c:trace_dump_set_overwrite]

## Invariants
- [Kconfig:CONFIG_SYSTEM_TRACE]: Build and feature compilation gated by `CONFIG_SYSTEM_TRACE`.
- [Kconfig:CONFIG_SYSTEM_TRACE_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_TRACE_PROGNAME`.
- [Kconfig:depends on DRIVERS_NOTECTL]: Requires Kconfig dependency condition `DRIVERS_NOTECTL`.
- [trace.h:CONFIG_DRIVERS_NOTERAM]: Conditional compilation gated by `CONFIG_DRIVERS_NOTERAM`.
- [trace.c:CONFIG_DRIVERS_NOTERAM]: Conditional compilation gated by `CONFIG_DRIVERS_NOTERAM`.
- [trace.c:CONFIG_SYSTEM_SYSTEM]: Conditional compilation gated by `CONFIG_SYSTEM_SYSTEM`.

## Side Effects
- [trace.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [trace.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [trace.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [trace_dump.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [trace_dump.c:open]: Performs VFS file or device descriptor I/O operations.
- [trace_dump.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
