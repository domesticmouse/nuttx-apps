# `netutils/dhcpd`

## Overview
Provides DHCP server (`netutils/dhcpd`). Enable support for the DHCP server.

## Interface
- [Kconfig:CONFIG_NETUTILS_DHCPD]
- [Kconfig:CONFIG_NETUTILS_DHCPD_HOST]
- [Kconfig:CONFIG_NETUTILS_DHCPD_IGNOREBROADCAST]
- [Kconfig:CONFIG_NETUTILS_DHCPD_LEASETIME]
- [dhcpd.c:struct lease_s]
- [dhcpd.c:struct dhcpmsg_s]
- [dhcpd.c:enum dhcpd_daemon_e]
- [dhcpd.c:struct dhcpd_state_s]
- [dhcpd.c:struct dhcpd_daemon_s]
- [dhcpd.c:struct dhcpd_config_s]
- [dhcpd.c:dhcpd_setlease]
- [dhcpd.c:dhcpd_sendack]
- [dhcpd.c:dhcpd_run]
- [dhcpd.c:dhcpd_start]
- [dhcpd.c:dhcpd_stop]
- [dhcpd.c:dhcpd_set_startip]
- [dhcpd.c:dhcpd_set_routerip]
- [dhcpd.c:dhcpd_set_netmask]

## Invariants
- [Kconfig:CONFIG_NETUTILS_DHCPD]: Build and feature compilation gated by `CONFIG_NETUTILS_DHCPD`.
- [Kconfig:CONFIG_NETUTILS_DHCPD_HOST]: Build and feature compilation gated by `CONFIG_NETUTILS_DHCPD_HOST`.
- [Kconfig:depends on NET_UDP]: Requires Kconfig dependency condition `NET_UDP`.
- [Kconfig:depends on EXPERIMENTAL]: Requires Kconfig dependency condition `EXPERIMENTAL`.
- [dhcpd.c:CONFIG_NETUTILS_DHCPD_HOST]: Conditional compilation gated by `CONFIG_NETUTILS_DHCPD_HOST`.
- [dhcpd.c:CONFIG_NETUTILS_DHCPD_LEASETIME]: Conditional compilation gated by `CONFIG_NETUTILS_DHCPD_LEASETIME`.

## Side Effects
- [dhcpd.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [dhcpd.c:close]: Performs VFS file or device descriptor I/O operations.
- [dhcpd.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [dhcpd.c:malloc]: Allocates or releases dynamic heap memory.
- [dhcpd.c:task_create]: Spawns child tasks, pthreads, or built-in applications.
- [dhcpd.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
