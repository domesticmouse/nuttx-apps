# `netutils/dhcpc`

## Overview
Provides DHCP client (`netutils/dhcpc`). Enable support for the DHCP client.

## Interface
- [Kconfig:CONFIG_NETUTILS_DHCPC]
- [Kconfig:CONFIG_NETUTILS_DHCPC_HOST_NAME]
- [Kconfig:CONFIG_NETUTILS_DHCPC_RECV_TIMEOUT_MS]
- [Kconfig:CONFIG_NETUTILS_DHCPC_RETRIES]
- [dhcpc.c:struct dhcp_msg]
- [dhcpc.c:struct dhcpc_state_s]
- [dhcpc.c:dhcpc_open]
- [dhcpc.c:dhcpc_close]
- [dhcpc.c:dhcpc_cancel]
- [dhcpc.c:dhcpc_request]
- [dhcpc.c:dhcpc_request_async]
- [dhcpc.c:dhcpc_release]

## Invariants
- [Kconfig:CONFIG_NETUTILS_DHCPC]: Build and feature compilation gated by `CONFIG_NETUTILS_DHCPC`.
- [Kconfig:CONFIG_NETUTILS_DHCPC_HOST_NAME]: Build and feature compilation gated by `CONFIG_NETUTILS_DHCPC_HOST_NAME`.
- [Kconfig:depends on NET_UDP]: Requires Kconfig dependency condition `NET_UDP`.
- [dhcpc.c:CONFIG_NET_DHCP_LIGHT]: Conditional compilation gated by `CONFIG_NET_DHCP_LIGHT`.
- [dhcpc.c:CONFIG_ENABLE_ALL_SIGNALS]: Conditional compilation gated by `CONFIG_ENABLE_ALL_SIGNALS`.
- [dhcpc.c:CONFIG_NET_BINDTODEVICE]: Conditional compilation gated by `CONFIG_NET_BINDTODEVICE`.

## Side Effects
- [dhcpc.c:close]: Performs VFS file or device descriptor I/O operations.
- [dhcpc.c:sendto]: Performs network socket creation, binding, or protocol I/O.
- [dhcpc.c:malloc]: Allocates or releases dynamic heap memory.
- [dhcpc.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
