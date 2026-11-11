# `system/dd`

## Overview
Provides system 'dd' command (`system/dd`). Enable support for the system 'dd' command.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_DD_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_DD]
- [Kconfig:CONFIG_SYSTEM_DD_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_DD_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_DD_STACKSIZE]
- [dd_main.c:struct dd_s]
- [dd_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_DD]: Build and feature compilation gated by `CONFIG_SYSTEM_DD`.
- [Kconfig:CONFIG_SYSTEM_DD_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_DD_PROGNAME`.
- [dd_main.c:CONFIG_SYSTEM_DD_PROGNAME]: Conditional compilation gated by `CONFIG_SYSTEM_DD_PROGNAME`.
- [dd_main.c:CONFIG_SYSTEM_DD_STATS]: Conditional compilation gated by `CONFIG_SYSTEM_DD_STATS`.

## Side Effects
- [dd_main.c:write]: Performs VFS file or device descriptor I/O operations.
- [dd_main.c:malloc]: Allocates or releases dynamic heap memory.
- [dd_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
