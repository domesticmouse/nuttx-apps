# `netutils/ping`

## Overview
Provides ICMP ping support (`netutils/ping`). Build in support for a IPv4 ping command. This command ping will send the ICMP ECHO_REQUEST and wait for the ICMP ECHO_RESPONSE from

## Interface
- [Kconfig:CONFIG_NETUTILS_PING]
- [Kconfig:CONFIG_NETUTILS_PING6]
- [icmp_ping.c:struct ping_priv_s]
- [icmp_ping.c:icmp_ping]
- [icmpv6_ping.c:icmp6_ping]

## Invariants
- [Kconfig:CONFIG_NETUTILS_PING]: Build and feature compilation gated by `CONFIG_NETUTILS_PING`.
- [Kconfig:CONFIG_NETUTILS_PING6]: Build and feature compilation gated by `CONFIG_NETUTILS_PING6`.
- [Kconfig:depends on NET_ICMP]: Requires Kconfig dependency condition `NET_ICMP`.
- [Kconfig:depends on NET_ICMPv6]: Requires Kconfig dependency condition `NET_ICMPv6`.
- [icmp_ping.c:CONFIG_LIBC_NETDB]: Conditional compilation gated by `CONFIG_LIBC_NETDB`.
- [icmp_ping.c:CONFIG_ENABLE_ALL_SIGNALS]: Conditional compilation gated by `CONFIG_ENABLE_ALL_SIGNALS`.

## Side Effects
- [icmp_ping.c:close]: Performs VFS file or device descriptor I/O operations.
- [icmp_ping.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [icmp_ping.c:malloc]: Allocates or releases dynamic heap memory.
- [icmpv6_ping.c:close]: Performs VFS file or device descriptor I/O operations.
- [icmpv6_ping.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [icmpv6_ping.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
