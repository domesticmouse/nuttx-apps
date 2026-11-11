# `netutils/netlib`

## Overview
Provides Network support library (`netutils/netlib`). Enable support for the network support library.

## Interface
- [Kconfig:CONFIG_NETUTILS_NETLIB]
- [Kconfig:CONFIG_NETUTILS_NETLIB_GENERICURLPARSER]
- [netlib_addipv6addr.c:netlib_add_ipv6addr]
- [netlib_addvlan.c:netlib_add_vlan]
- [netlib_autoconfig.c:netlib_icmpv6_autoconfiguration]
- [netlib_bridge.c:netlib_add_bridge]
- [netlib_bridge.c:netlib_del_bridge]
- [netlib_bridge.c:netlib_bridge_addif]
- [netlib_bridge.c:netlib_bridge_delif]
- [netlib_checkhttpconnectivity.c:netlib_check_httpconnectivity]
- [netlib_checkifconflict.c:netlib_check_ifconflict]
- [netlib_checkifconnectivity.c:netlib_check_ifconnectivity]
- [netlib_checkipconnectivity.c:netlib_check_ipconnectivity]
- [netlib_conntrack.c:struct netlib_conntrack_sendto_request_s]
- [netlib_conntrack.c:netlib_parse_conntrack]
- [netlib_conntrack.c:netlib_get_conntrack]
- [netlib_delarp.c:netlib_del_arpmapping]
- [netlib_delipv4dnsaddr.c:netlib_del_ipv4dnsaddr]

## Invariants
- [Kconfig:CONFIG_NETUTILS_NETLIB]: Build and feature compilation gated by `CONFIG_NETUTILS_NETLIB`.
- [Kconfig:CONFIG_NETUTILS_NETLIB_GENERICURLPARSER]: Build and feature compilation gated by `CONFIG_NETUTILS_NETLIB_GENERICURLPARSER`.
- [Kconfig:depends on NET]: Requires Kconfig dependency condition `NET`.
- [netlib_addvlan.c:CONFIG_NET_VLAN]: Conditional compilation gated by `CONFIG_NET_VLAN`.
- [netlib_checkhttpconnectivity.c:CONFIG_LIBC_NETDB]: Conditional compilation gated by `CONFIG_LIBC_NETDB`.
- [netlib_checkifconflict.c:CONFIG_NET_ARP_ACD]: Conditional compilation gated by `CONFIG_NET_ARP_ACD`.

## Side Effects
- [netlib_addipv6addr.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [netlib_addipv6addr.c:close]: Performs VFS file or device descriptor I/O operations.
- [netlib_addipv6addr.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [netlib_addvlan.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [netlib_addvlan.c:close]: Performs VFS file or device descriptor I/O operations.
- [netlib_addvlan.c:socket]: Performs network socket creation, binding, or protocol I/O.

## Verification
- Run: `make test`
