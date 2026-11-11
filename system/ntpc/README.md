# `system/ntpc`

## Overview
Provides NTP Daemon Commands (`system/ntpc`). Enable the NTP client example. This example provides a command-line interface to manage the NTP client for time synchronization.

## Interface
- [Makefile:PROGNAME=ntpcstart]
- [Kconfig:CONFIG_SYSTEM_NTPC]
- [Kconfig:CONFIG_SYSTEM_NTPC_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_NTPC_STACKSIZE]
- [ntpcstart_main.c:main]
- [ntpcstatus_main.c:main]
- [ntpcstop_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NTPC]: Build and feature compilation gated by `CONFIG_SYSTEM_NTPC`.
- [Kconfig:CONFIG_SYSTEM_NTPC_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_NTPC_PRIORITY`.
- [Kconfig:depends on NET_UDP]: Requires Kconfig dependency condition `NET_UDP`.
- [ntpcstatus_main.c:CONFIG_LIBC_NETDB]: Conditional compilation gated by `CONFIG_LIBC_NETDB`.

## Side Effects
- [ntpcstart_main.c:printf]: Writes formatted diagnostic, logging, or console output.
- [ntpcstatus_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [ntpcstop_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
