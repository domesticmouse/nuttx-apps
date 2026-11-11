# `system/telnetd`

## Overview
Provides Telnet daemon application (`system/telnetd`). Enable the Telnet daemon application

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_TELNETD_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_TELNETD]
- [Kconfig:CONFIG_SYSTEM_TELNETD_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_TELNETD_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_TELNETD_STACKSIZE]
- [telnetd.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_TELNETD]: Build and feature compilation gated by `CONFIG_SYSTEM_TELNETD`.
- [Kconfig:CONFIG_SYSTEM_TELNETD_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_TELNETD_PROGNAME`.
- [Kconfig:depends on NETUTILS_TELNETD]: Requires Kconfig dependency condition `NETUTILS_TELNETD`.
- [telnetd.c:CONFIG_BUILD_KERNEL]: Conditional compilation gated by `CONFIG_BUILD_KERNEL`.
- [telnetd.c:CONFIG_LIBC_EXECFUNCS]: Conditional compilation gated by `CONFIG_LIBC_EXECFUNCS`.

## Side Effects
- [telnetd.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
