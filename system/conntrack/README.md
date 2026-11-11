# `system/conntrack`

## Overview
Provides conntrack command (`system/conntrack`). Enable support for the 'conntrack' command, a simple tool like Linux's 'conntrack', only supports printing NAT connections now.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_CONNTRACK_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_CONNTRACK]
- [Kconfig:CONFIG_SYSTEM_CONNTRACK_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_CONNTRACK_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_CONNTRACK_STACKSIZE]
- [conntrack.c:struct conntrack_args_s]
- [conntrack.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_CONNTRACK]: Build and feature compilation gated by `CONFIG_SYSTEM_CONNTRACK`.
- [Kconfig:CONFIG_SYSTEM_CONNTRACK_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_CONNTRACK_PROGNAME`.
- [Kconfig:depends on NETLINK_NETFILTER]: Requires Kconfig dependency condition `NETLINK_NETFILTER`.

## Side Effects
- [conntrack.c:close]: Performs VFS file or device descriptor I/O operations.
- [conntrack.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [conntrack.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
