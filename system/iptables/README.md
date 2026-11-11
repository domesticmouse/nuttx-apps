# `system/iptables`

## Overview
Provides 'iptables' command (`system/iptables`). Enable support for the 'iptables' command.

## Interface
- [Makefile:PROGNAME=iptables]
- [Makefile:PROGNAME=ip6tables]
- [Kconfig:CONFIG_SYSTEM_IPTABLES]
- [Kconfig:CONFIG_SYSTEM_IP6TABLES]
- [Kconfig:CONFIG_SYSTEM_IPTABLES_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_IPTABLES_STACKSIZE]
- [iptables.h:enum iptables_command_e]
- [iptables.h:struct iptables_args_s]
- [iptables.h:iptables_parse]
- [iptables.h:iptables_parse_ip]
- [iptables.h:iptables_parse_ports]
- [iptables.h:iptables_parse_icmp]
- [iptables.h:iptables_showusage]
- [iptables.h:iptables_hook2str]
- [iptables.h:iptables_target2str]
- [iptables.h:iptables_proto2str]
- [iptables.h:iptables_match2str]
- [ip6tables.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_IPTABLES]: Build and feature compilation gated by `CONFIG_SYSTEM_IPTABLES`.
- [Kconfig:CONFIG_SYSTEM_IP6TABLES]: Build and feature compilation gated by `CONFIG_SYSTEM_IP6TABLES`.
- [Kconfig:depends on NET_IPTABLES && NET_IPv4]: Requires Kconfig dependency condition `NET_IPTABLES && NET_IPv4`.
- [Kconfig:depends on NET_IPTABLES && NET_IPv6]: Requires Kconfig dependency condition `NET_IPTABLES && NET_IPv6`.
- [Kconfig:depends on FS_LOCK_BUCKET_SIZE > 0]: Requires Kconfig dependency condition `FS_LOCK_BUCKET_SIZE > 0`.
- [ip6tables.c:CONFIG_NET_IPFILTER]: Conditional compilation gated by `CONFIG_NET_IPFILTER`.

## Side Effects
- [ip6tables.c:free]: Allocates or releases dynamic heap memory.
- [ip6tables.c:printf]: Writes formatted diagnostic, logging, or console output.
- [iptables.c:open]: Performs VFS file or device descriptor I/O operations.
- [iptables.c:free]: Allocates or releases dynamic heap memory.
- [iptables.c:printf]: Writes formatted diagnostic, logging, or console output.
- [iptables_utils.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
