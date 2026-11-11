# `wireless/ieee802154/i8shark`

## Overview
Provides IEEE 802.15.4 Wireshark adapter (`wireless/ieee802154/i8shark`). The default path to MAC character driver. Default: /dev/ieee0

## Interface
- [Makefile:PROGNAME=i8shark]
- [Kconfig:CONFIG_IEEE802154_I8SHARK]
- [Kconfig:CONFIG_IEEE802154_I8SHARK_DAEMON_PRIORITY]
- [Kconfig:CONFIG_IEEE802154_I8SHARK_DAEMON_STACKSIZE]
- [Kconfig:CONFIG_IEEE802154_I8SHARK_DEVPATH]
- [i8shark_main.c:struct i8shark_state_s]
- [i8shark_main.c:main]

## Invariants
- [Kconfig:CONFIG_IEEE802154_I8SHARK]: Build and feature compilation gated by `CONFIG_IEEE802154_I8SHARK`.
- [Kconfig:CONFIG_IEEE802154_I8SHARK_DAEMON_PRIORITY]: Build and feature compilation gated by `CONFIG_IEEE802154_I8SHARK_DAEMON_PRIORITY`.
- [Kconfig:depends on IEEE802154_MACDEV && NET_UDP && NET_IPv4]: Requires Kconfig dependency condition `IEEE802154_MACDEV && NET_UDP && NET_IPv4`.
- [i8shark_main.c:CONFIG_IEEE802154_I8SHARK_DAEMON_PRIORITY]: Conditional compilation gated by `CONFIG_IEEE802154_I8SHARK_DAEMON_PRIORITY`.
- [i8shark_main.c:CONFIG_IEEE802154_I8SHARK_DAEMON_STACKSIZE]: Conditional compilation gated by `CONFIG_IEEE802154_I8SHARK_DAEMON_STACKSIZE`.
- [i8shark_main.c:CONFIG_IEEE802154_I8SHARK_CHANNEL]: Conditional compilation gated by `CONFIG_IEEE802154_I8SHARK_CHANNEL`.

## Side Effects
- [i8shark_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [i8shark_main.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [i8shark_main.c:task_create]: Spawns child tasks, pthreads, or built-in applications.
- [i8shark_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
