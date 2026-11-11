# `wireless/bluetooth/btsak`

## Overview
Provides Bluetooth Swiss Army Knife (`wireless/bluetooth/btsak`). Enable the Bluetooth Swiss Army Knife

## Interface
- [Makefile:PROGNAME=$(CONFIG_BTSAK_PROGNAME)]
- [Kconfig:CONFIG_BTSAK]
- [Kconfig:CONFIG_BTSAK_PROGNAME]
- [Kconfig:CONFIG_BTSAK_PRIORITY]
- [Kconfig:CONFIG_BTSAK_STACKSIZE]
- [btsak.h:struct btsak_s]
- [btsak.h:btsak_update_ipv6addr]
- [btsak.h:btsak_char2nibble]
- [btsak.h:btsak_str2long]
- [btsak.h:btsak_str2uint8]
- [btsak.h:btsak_str2uint16]
- [btsak.h:btsak_str2bool]
- [btsak.h:btsak_str2payload]
- [btsak.h:btsak_str2addr]
- [btsak.h:btsak_str2addrtype]
- [btsak.h:btsak_str2seclevel]
- [btsak.h:btsak_socket]
- [btsak.h:btsak_showusage]

## Invariants
- [Kconfig:CONFIG_BTSAK]: Build and feature compilation gated by `CONFIG_BTSAK`.
- [Kconfig:CONFIG_BTSAK_PROGNAME]: Build and feature compilation gated by `CONFIG_BTSAK_PROGNAME`.
- [Kconfig:depends on WIRELESS_BLUETOOTH_HOST]: Requires Kconfig dependency condition `WIRELESS_BLUETOOTH_HOST`.
- [btsak.h:CONFIG_NET_BLUETOOTH]: Conditional compilation gated by `CONFIG_NET_BLUETOOTH`.
- [btsak.h:CONFIG_NET_6LOWPAN]: Conditional compilation gated by `CONFIG_NET_6LOWPAN`.
- [btsak_main.c:CONFIG_NET_BLUETOOTH]: Conditional compilation gated by `CONFIG_NET_BLUETOOTH`.

## Side Effects
- [btsak_advertise.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [btsak_advertise.c:close]: Performs VFS file or device descriptor I/O operations.
- [btsak_advertise.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [btsak_features.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [btsak_features.c:close]: Performs VFS file or device descriptor I/O operations.
- [btsak_features.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
