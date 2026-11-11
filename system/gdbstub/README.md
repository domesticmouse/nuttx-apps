# `system/gdbstub`

## Overview
Provides GDBSTUB (`system/gdbstub`). Enable support for gdbstub.

## Interface
- [Makefile:PROGNAME=gdbstub]
- [Kconfig:CONFIG_SYSTEM_GDBSTUB]
- [Kconfig:CONFIG_SYSTEM_GDBSTUB_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_GDBSTUB_PRIORITY]
- [gdbstub.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_GDBSTUB]: Build and feature compilation gated by `CONFIG_SYSTEM_GDBSTUB`.
- [Kconfig:CONFIG_SYSTEM_GDBSTUB_STACKSIZE]: Build and feature compilation gated by `CONFIG_SYSTEM_GDBSTUB_STACKSIZE`.
- [Kconfig:depends on LIB_GDBSTUB]: Requires Kconfig dependency condition `LIB_GDBSTUB`.
- [gdbstub.c:CONFIG_PIPES]: Conditional compilation gated by `CONFIG_PIPES`.
- [gdbstub.c:CONFIG_LIBC_EXECFUNCS]: Conditional compilation gated by `CONFIG_LIBC_EXECFUNCS`.
- [gdbstub.c:CONFIG_NET]: Conditional compilation gated by `CONFIG_NET`.

## Side Effects
- [gdbstub.c:fread]: Performs VFS file or device descriptor I/O operations.
- [gdbstub.c:send]: Performs network socket creation, binding, or protocol I/O.
- [gdbstub.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
