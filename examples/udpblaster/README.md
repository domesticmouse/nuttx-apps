# udpblaster

## Overview
UDP blaster example (`udpblaster`). Enable the network test example

## Interface
- `[Kconfig:EXAMPLES_UDPBLASTER]` - Build configuration option `EXAMPLES_UDPBLASTER`
- `[Kconfig:EXAMPLES_UDPBLASTER_PROGNAME]` - Build configuration option `EXAMPLES_UDPBLASTER_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_UDPBLASTER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_UDPBLASTER_PROGNAME}`
- `[udpblaster_host.c:main]` - Application entry point `main()`
- `[udpblaster_target.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_UDP]` - Requires kernel/app configuration `NET_UDP`
- `[Kconfig:depends on NET_IPv4]` - Requires kernel/app configuration `NET_IPv4`
- `[Kconfig:depends on NET_IPv6]` - Requires kernel/app configuration `NET_IPv6`
- `[udpblaster.h:#error]` - Compile-time precondition: Additional link layer definitions needed
- `[udpblaster.h:CONFIG_NET_SOLINGER]` - Configuration guard on `CONFIG_NET_SOLINGER`
- `[udpblaster.h:CONFIG_EXAMPLES_UDPBLASTER_IP]` - Configuration guard on `CONFIG_EXAMPLES_UDPBLASTER_IP`
- `[udpblaster.h:CONFIG_NET_6LOWPAN]` - Configuration guard on `CONFIG_NET_6LOWPAN`
- `[udpblaster.h:CONFIG_NET_ETHERNET]` - Configuration guard on `CONFIG_NET_ETHERNET`
- `[udpblaster_host.c:CONFIG_EXAMPLES_UDPBLASTER_IP]` - Configuration guard on `CONFIG_EXAMPLES_UDPBLASTER_IP`
- `[udpblaster_target.c:CONFIG_EXAMPLES_UDPBLASTER_INIT]` - Configuration guard on `CONFIG_EXAMPLES_UDPBLASTER_INIT`
- `[udpblaster_target.c:CONFIG_EXAMPLES_UDPBLASTER_IP]` - Configuration guard on `CONFIG_EXAMPLES_UDPBLASTER_IP`
- `[udpblaster_target.c:CONFIG_EXAMPLES_UDPBLASTER_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_UDPBLASTER_NOMAC`
- `[udpblaster_target.c:CONFIG_NET_ICMP]` - Configuration guard on `CONFIG_NET_ICMP`

## Side Effects
- `[udpblaster_host.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[udpblaster_host.c:sendto]` - Sends datagram packets via `sendto()`
- `[udpblaster_target.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[udpblaster_target.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[udpblaster_target.c:sendto]` - Sends datagram packets via `sendto()`
- `[udpblaster_target.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
