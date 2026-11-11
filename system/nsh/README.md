# `system/nsh`

## Overview
Provides NuttShell (NSH) example (`system/nsh`). Enable the NuttShell (NSH) example

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_NSH_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_NSH]
- [Kconfig:CONFIG_SYSTEM_NSH_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_NSH_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_NSH_PROGNAME]
- [nsh_main.c:main]
- [sh_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NSH]: Build and feature compilation gated by `CONFIG_SYSTEM_NSH`.
- [Kconfig:CONFIG_SYSTEM_NSH_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_NSH_PRIORITY`.
- [nsh_main.c:CONFIG_NSH_CONSOLE]: Conditional compilation gated by `CONFIG_NSH_CONSOLE`.

## Side Effects
- [nsh_main.c:dprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
