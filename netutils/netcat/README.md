# `netutils/netcat`

## Overview
Provides NetCat tool (`netutils/netcat`). Enable the NetCat TCP/IP swiss army tool

## Interface
- [Makefile:PROGNAME=$(CONFIG_NETUTILS_NETCAT_PROGNAME)]
- [Kconfig:CONFIG_NETUTILS_NETCAT]
- [Kconfig:CONFIG_NETUTILS_NETCAT_PROGNAME]
- [Kconfig:CONFIG_NETUTILS_NETCAT_PRIORITY]
- [Kconfig:CONFIG_NETUTILS_NETCAT_STACKSIZE]
- [netcat_main.c:do_io]
- [netcat_main.c:do_io_over_sendfile]
- [netcat_main.c:netcat_server]
- [netcat_main.c:netcat_client]
- [netcat_main.c:main]

## Invariants
- [Kconfig:CONFIG_NETUTILS_NETCAT]: Build and feature compilation gated by `CONFIG_NETUTILS_NETCAT`.
- [Kconfig:CONFIG_NETUTILS_NETCAT_PROGNAME]: Build and feature compilation gated by `CONFIG_NETUTILS_NETCAT_PROGNAME`.
- [Kconfig:depends on NET_TCP]: Requires Kconfig dependency condition `NET_TCP`.
- [Kconfig:depends on NET_SENDFILE]: Requires Kconfig dependency condition `NET_SENDFILE`.
- [netcat_main.c:CONFIG_NETUTILS_NETCAT_SENDFILE]: Conditional compilation gated by `CONFIG_NETUTILS_NETCAT_SENDFILE`.

## Side Effects
- [netcat_main.c:read]: Performs VFS file or device descriptor I/O operations.
- [netcat_main.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [netcat_main.c:malloc]: Allocates or releases dynamic heap memory.
- [netcat_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
