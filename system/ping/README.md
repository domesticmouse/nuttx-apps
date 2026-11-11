# `system/ping`

## Overview
Provides ICMP 'ping' command (`system/ping`). Enable support for the ICMP 'ping' command.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_PING_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_PING]
- [Kconfig:CONFIG_SYSTEM_PING_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_PING_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_PING_STACKSIZE]
- [ping.c:struct ping_priv_s]
- [ping.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_PING]: Build and feature compilation gated by `CONFIG_SYSTEM_PING`.
- [Kconfig:CONFIG_SYSTEM_PING_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_PING_PROGNAME`.
- [Kconfig:depends on NET_IPv4]: Requires Kconfig dependency condition `NET_IPv4`.
- [ping.c:CONFIG_SYSTEM_PING6]: Conditional compilation gated by `CONFIG_SYSTEM_PING6`.
- [ping.c:CONFIG_LIBC_EXECFUNCS]: Conditional compilation gated by `CONFIG_LIBC_EXECFUNCS`.
- [ping.c:CONFIG_LIBC_NETDB]: Conditional compilation gated by `CONFIG_LIBC_NETDB`.

## Side Effects
- [ping.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [ping.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
