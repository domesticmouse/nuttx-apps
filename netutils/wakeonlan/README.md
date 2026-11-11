# `netutils/wakeonlan`

## Overview
Provides WakeOnLAN support (`netutils/wakeonlan`). Enable the wake on LAN command "wol". This command sends a WakeOnLAN magic packet to target MAC address.

## Interface
- [Makefile:PROGNAME=$(CONFIG_NETUTILS_WAKEONLAN_PROGNAME)]
- [Kconfig:CONFIG_NETUTILS_WAKEONLAN]
- [Kconfig:CONFIG_NETUTILS_WAKEONLAN_PROGNAME]
- [Kconfig:CONFIG_NETUTILS_WAKEONLAN_PRIORITY]
- [Kconfig:CONFIG_NETUTILS_WAKEONLAN_STACKSIZE]
- [wol_main.c:main]

## Invariants
- [Kconfig:CONFIG_NETUTILS_WAKEONLAN]: Build and feature compilation gated by `CONFIG_NETUTILS_WAKEONLAN`.
- [Kconfig:CONFIG_NETUTILS_WAKEONLAN_PROGNAME]: Build and feature compilation gated by `CONFIG_NETUTILS_WAKEONLAN_PROGNAME`.
- [Kconfig:depends on NET_UDP && NET_SOCKOPTS]: Requires Kconfig dependency condition `NET_UDP && NET_SOCKOPTS`.

## Side Effects
- [wol_main.c:close]: Performs VFS file or device descriptor I/O operations.
- [wol_main.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [wol_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
