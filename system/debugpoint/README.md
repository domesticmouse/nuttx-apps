# `system/debugpoint`

## Overview
Provides Debugpoint utility (`system/debugpoint`). Enable the DEBUGPOINT test program. It is a simple utility for testing the debug point support and

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_DEBUGPOINT_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_DEBUGPOINT]
- [Kconfig:CONFIG_SYSTEM_DEBUGPOINT_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_DEBUGPOINT_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_DEBUGPOINT_STACKSIZE]
- [debug.c:struct debug_option]
- [debug.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_DEBUGPOINT]: Build and feature compilation gated by `CONFIG_SYSTEM_DEBUGPOINT`.
- [Kconfig:CONFIG_SYSTEM_DEBUGPOINT_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_DEBUGPOINT_PROGNAME`.
- [Kconfig:depends on ARCH_HAVE_DEBUG]: Requires Kconfig dependency condition `ARCH_HAVE_DEBUG`.
- [Kconfig:depends on LIB_GDBSTUB]: Requires Kconfig dependency condition `LIB_GDBSTUB`.

## Side Effects
- [debug.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
