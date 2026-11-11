# `system/ping6`

## Overview
Provides ICMPv6 'ping6' command (`system/ping6`). Enable support for the ICMP 'ping' command.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_PING6_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_PING6]
- [Kconfig:CONFIG_SYSTEM_PING6_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_PING6_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_PING6_STACKSIZE]
- [ping6.c:struct ping6_priv_s]
- [ping6.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_PING6]: Build and feature compilation gated by `CONFIG_SYSTEM_PING6`.
- [Kconfig:CONFIG_SYSTEM_PING6_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_PING6_PROGNAME`.
- [ping6.c:CONFIG_LIBC_NETDB]: Conditional compilation gated by `CONFIG_LIBC_NETDB`.
- [ping6.c:CONFIG_NETDB_DNSCLIENT]: Conditional compilation gated by `CONFIG_NETDB_DNSCLIENT`.
- [ping6.c:CONFIG_NET_BINDTODEVICE]: Conditional compilation gated by `CONFIG_NET_BINDTODEVICE`.

## Side Effects
- [ping6.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [ping6.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
