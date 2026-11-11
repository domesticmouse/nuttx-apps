# bridge

## Overview
UDP bridge example (`bridge`). Simple test of a system with multiple networks.  It simply echoes all UDP packets received on network 1 and network 2 to network 2 and network 1, respectively.  Interface 1 and interface may or may not lie on the same network.

## Interface
- `[Kconfig:EXAMPLES_BRIDGE]` - Build configuration option `EXAMPLES_BRIDGE`
- `[Kconfig:EXAMPLES_BRIDGE_NET1_IFNAME]` - Build configuration option `EXAMPLES_BRIDGE_NET1_IFNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `bridge`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `bridge`
- `[bridge_main.c:main]` - Application entry point `main()`
- `[host_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_UDP && !NET_IPv6]` - Requires kernel/app configuration `NET_UDP && !NET_IPv6`
- `[Kconfig:depends on EXAMPLES_BRIDGE_NET1_NOMAC]` - Requires kernel/app configuration `EXAMPLES_BRIDGE_NET1_NOMAC`
- `[Kconfig:depends on !EXAMPLES_BRIDGE_NET1_DHCPC]` - Requires kernel/app configuration `!EXAMPLES_BRIDGE_NET1_DHCPC`
- `[bridge_main.c:CONFIG_EXAMPLES_BRIDGE_NET1_DHCPC]` - Configuration guard on `CONFIG_EXAMPLES_BRIDGE_NET1_DHCPC`
- `[bridge_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`
- `[bridge_main.c:CONFIG_EXAMPLES_BRIDGE_NET1_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_BRIDGE_NET1_NOMAC`
- `[bridge_main.c:CONFIG_EXAMPLES_BRIDGE_NET2_DHCPC]` - Configuration guard on `CONFIG_EXAMPLES_BRIDGE_NET2_DHCPC`
- `[host_net1.c:CONFIG_EXAMPLES_BRIDGE_NET1_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_BRIDGE_NET1_NOMAC`
- `[host_net1.c:CONFIG_EXAMPLES_BRIDGE_NET2_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_BRIDGE_NET2_NOMAC`
- `[host_net2.c:CONFIG_EXAMPLES_BRIDGE_NET2_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_BRIDGE_NET2_NOMAC`
- `[host_net2.c:CONFIG_EXAMPLES_BRIDGE_NET1_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_BRIDGE_NET1_NOMAC`

## Side Effects
- `[bridge_main.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[bridge_main.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[bridge_main.c:sendto]` - Sends datagram packets via `sendto()`
- `[bridge_main.c:recvfrom]` - Receives datagram packets via `recvfrom()`
- `[bridge_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[bridge_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[host_main.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[host_main.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[host_main.c:sendto]` - Sends datagram packets via `sendto()`
- `[host_main.c:recvfrom]` - Receives datagram packets via `recvfrom()`
- `[host_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
