# `system/telnet`

## Overview
Provides Telnet chat daemon (`system/telnet`). Enable the Telnet Chat daemon.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_TELNET_CHATD_PROGNAME)]
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_TELNET_CLIENT_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_TELNET_CHATD]
- [Kconfig:CONFIG_SYSTEM_TELNET_CHATD_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_TELNET_CHATD_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_TELNET_CHATD_PRIORITY]
- [telnet_chatd.c:struct user_s]
- [telnet_chatd.c:main]
- [telnet_client.c:server]
- [telnet_client.c:local]
- [telnet_client.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_TELNET_CHATD]: Build and feature compilation gated by `CONFIG_SYSTEM_TELNET_CHATD`.
- [Kconfig:CONFIG_SYSTEM_TELNET_CHATD_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_TELNET_CHATD_PROGNAME`.
- [Kconfig:depends on NET && NET_TCP]: Requires Kconfig dependency condition `NET && NET_TCP`.
- [telnet_client.c:CONFIG_SYSTEM_TELNETD_PORT]: Conditional compilation gated by `CONFIG_SYSTEM_TELNETD_PORT`.

## Side Effects
- [telnet_chatd.c:close]: Performs VFS file or device descriptor I/O operations.
- [telnet_chatd.c:send]: Performs network socket creation, binding, or protocol I/O.
- [telnet_chatd.c:free]: Allocates or releases dynamic heap memory.
- [telnet_chatd.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [telnet_client.c:fwrite]: Performs VFS file or device descriptor I/O operations.
- [telnet_client.c:send]: Performs network socket creation, binding, or protocol I/O.

## Verification
- Run: `make test`
