# `system/tcpdump`

## Overview
Provides tcpdump command (`system/tcpdump`). Enable support for the 'tcpdump' command.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_TCPDUMP_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_TCPDUMP]
- [Kconfig:CONFIG_SYSTEM_TCPDUMP_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_TCPDUMP_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_TCPDUMP_STACKSIZE]
- [tcpdump.c:struct pcap_filehdr_s]
- [tcpdump.c:struct pcap_pkthdr_s]
- [tcpdump.c:struct tcpdump_args_s]
- [tcpdump.c:struct tcpdump_cfgs_s]
- [tcpdump.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_TCPDUMP]: Build and feature compilation gated by `CONFIG_SYSTEM_TCPDUMP`.
- [Kconfig:CONFIG_SYSTEM_TCPDUMP_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_TCPDUMP_PROGNAME`.
- [Kconfig:depends on NET_PKT]: Requires Kconfig dependency condition `NET_PKT`.

## Side Effects
- [tcpdump.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [tcpdump.c:write]: Performs VFS file or device descriptor I/O operations.
- [tcpdump.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [tcpdump.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
