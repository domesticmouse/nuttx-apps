# udp

## Overview
UDP example (`udp`). Enable the UDP example

## Interface
- `[Kconfig:EXAMPLES_UDP]` - Build configuration option `EXAMPLES_UDP`
- `[Kconfig:EXAMPLES_UDP_SERVER1]` - Build configuration option `EXAMPLES_UDP_SERVER1`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_UDP_PROGNAME1)`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_UDP_PROGNAME2)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_UDP_PROGNAME1}`
- `[udp.h:udp_netinit]` - Public function declaration `udp_netinit()`
- `[udp.h:udp_cmdline]` - Public function declaration `udp_cmdline()`
- `[udp.h:udp_client]` - Public function declaration `udp_client()`
- `[udp.h:udp_server]` - Public function declaration `udp_server()`
- `[udp_client.c:udp_client]` - Public function `udp_client()`
- `[udp_cmdline.c:udp_cmdline]` - Public function `udp_cmdline()`
- `[udp_host.c:main]` - Application entry point `main()`
- `[udp_netinit.c:udp_netinit]` - Public function `udp_netinit()`
- `[udp_server.c:udp_server]` - Public function `udp_server()`
- `[udp_target1.c:main]` - Application entry point `main()`
- `[udp_target2.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_UDP]` - Requires kernel/app configuration `NET_UDP`
- `[Kconfig:depends on NET_IPv4]` - Requires kernel/app configuration `NET_IPv4`
- `[Kconfig:depends on NET_IPv6]` - Requires kernel/app configuration `NET_IPv6`
- `[udp.h:CONFIG_EXAMPLES_UDP_IP]` - Configuration guard on `CONFIG_EXAMPLES_UDP_IP`
- `[udp.h:CONFIG_EXAMPLES_UDP_SERVER_PORTNO]` - Configuration guard on `CONFIG_EXAMPLES_UDP_SERVER_PORTNO`
- `[udp.h:CONFIG_EXAMPLES_UDP_CLIENT_PORTNO]` - Configuration guard on `CONFIG_EXAMPLES_UDP_CLIENT_PORTNO`
- `[udp.h:CONFIG_EXAMPLES_UDP_NETINIT]` - Configuration guard on `CONFIG_EXAMPLES_UDP_NETINIT`
- `[udp_client.c:CONFIG_EXAMPLES_UDP_IP]` - Configuration guard on `CONFIG_EXAMPLES_UDP_IP`
- `[udp_client.c:CONFIG_EXAMPLES_UDP_BROADCAST]` - Configuration guard on `CONFIG_EXAMPLES_UDP_BROADCAST`
- `[udp_cmdline.c:CONFIG_EXAMPLES_UDP_IP]` - Configuration guard on `CONFIG_EXAMPLES_UDP_IP`
- `[udp_cmdline.c:argc]` - Validates command-line argument count `argc`
- `[udp_host.c:CONFIG_EXAMPLES_UDP_SERVER1]` - Configuration guard on `CONFIG_EXAMPLES_UDP_SERVER1`
- `[udp_netinit.c:CONFIG_EXAMPLES_UDP_NETINIT]` - Configuration guard on `CONFIG_EXAMPLES_UDP_NETINIT`
- `[udp_netinit.c:CONFIG_EXAMPLES_UDP_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_UDP_DEVNAME`
- `[udp_netinit.c:CONFIG_EXAMPLES_UDP_IP]` - Configuration guard on `CONFIG_EXAMPLES_UDP_IP`
- `[udp_netinit.c:CONFIG_NET_ICMP]` - Configuration guard on `CONFIG_NET_ICMP`
- `[udp_server.c:CONFIG_EXAMPLES_UDP_IP]` - Configuration guard on `CONFIG_EXAMPLES_UDP_IP`
- `[udp_server.c:CONFIG_EXAMPLES_UDP_BROADCAST]` - Configuration guard on `CONFIG_EXAMPLES_UDP_BROADCAST`
- `[udp_target1.c:CONFIG_EXAMPLES_UDP_NETINIT]` - Configuration guard on `CONFIG_EXAMPLES_UDP_NETINIT`
- `[udp_target1.c:CONFIG_EXAMPLES_UDP_SERVER1]` - Configuration guard on `CONFIG_EXAMPLES_UDP_SERVER1`

## Side Effects
- `[udp_client.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[udp_client.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[udp_client.c:sendto]` - Sends datagram packets via `sendto()`
- `[udp_client.c:printf]` - Writes formatted output to standard output via `printf()`
- `[udp_server.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[udp_server.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[udp_server.c:recvfrom]` - Receives datagram packets via `recvfrom()`
- `[udp_server.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
