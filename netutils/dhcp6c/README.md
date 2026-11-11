# `netutils/dhcp6c`

## Overview
Implements DHCPv6 client (`netutils/dhcp6c`) for the NuttX application subsystem.

## Interface
- [Kconfig:CONFIG_NETUTILS_DHCP6C]
- [Kconfig:CONFIG_NETUTILS_DHCP6C_REQUEST_TIMEOUT]
- [dhcp6c.c:enum dhcpv6_opt_e]
- [dhcp6c.c:enum dhcpv6_opt_npt_e]
- [dhcp6c.c:enum dhcpv6_msg_e]
- [dhcp6c.c:enum dhcpv6_status_e]
- [dhcp6c.c:enum dhcpv6_mode_e]
- [dhcp6c.c:enum dhcpv6_state_e]
- [dhcp6c.c:enum dhcp6c_ia_mode_e]
- [dhcp6c.c:struct dhcpv6_server_cand_s]
- [dhcp6c.c:struct dhcp6c_retx_s]
- [dhcp6c.c:struct dhcp6c_state_s]
- [dhcp6c.c:end_packed_struct]
- [dhcp6c.c:fqdn]
- [dhcp6c.c:reconf_accept]
- [dhcp6c.c:hdr]
- [dhcp6c.c:dhcp6c_open]
- [dhcp6c.c:dhcp6c_request]

## Invariants
- [Kconfig:CONFIG_NETUTILS_DHCP6C]: Build and feature compilation gated by `CONFIG_NETUTILS_DHCP6C`.
- [Kconfig:CONFIG_NETUTILS_DHCP6C_REQUEST_TIMEOUT]: Build and feature compilation gated by `CONFIG_NETUTILS_DHCP6C_REQUEST_TIMEOUT`.
- [Kconfig:depends on NET_IPv6]: Requires Kconfig dependency condition `NET_IPv6`.
- [Kconfig:depends on NET_UDP && NET_UDP_CHECKSUMS]: Requires Kconfig dependency condition `NET_UDP && NET_UDP_CHECKSUMS`.

## Side Effects
- [dhcp6c.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [dhcp6c.c:read]: Performs VFS file or device descriptor I/O operations.
- [dhcp6c.c:setsockopt]: Performs network socket creation, binding, or protocol I/O.
- [dhcp6c.c:realloc]: Allocates or releases dynamic heap memory.
- [dhcp6c.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
