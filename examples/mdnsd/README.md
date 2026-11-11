# mdnsd

## Overview
MDNS daemon example (`mdnsd`). Enable the MDNS daemon example

## Interface
- `[Kconfig:EXAMPLES_MDNSD]` - Build configuration option `EXAMPLES_MDNSD`
- `[Kconfig:EXAMPLES_MDNS_SERVICE]` - Build configuration option `EXAMPLES_MDNS_SERVICE`
- `[Makefile:PROGNAME]` - Registers application/module target `mdnsd_start mdnsd_stop mdnsd_event`
- `[mdnsd_daemon.h:mdnsd_daemon]` - Public function declaration `mdnsd_daemon()`
- `[mdnsd_daemon.c:mdnsd_daemon]` - Public function `mdnsd_daemon()`
- `[mdnsd_event.c:main]` - Application entry point `main()`
- `[mdnsd_start.c:main]` - Application entry point `main()`
- `[mdnsd_stop.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NETUTILS_MDNS_DAEMON]` - Requires kernel/app configuration `NETUTILS_MDNS_DAEMON`
- `[mdnsd_daemon.c:#error]` - Compile-time precondition: You must define CONFIG_NET
- `[mdnsd_daemon.c:#error]` - Compile-time precondition: You must define CONFIG_NET_UDP
- `[mdnsd_daemon.c:#error]` - Compile-time precondition: You must define CONFIG_NET_BROADCAST
- `[mdnsd_daemon.c:CONFIG_NET]` - Configuration guard on `CONFIG_NET`
- `[mdnsd_daemon.c:CONFIG_NET_UDP]` - Configuration guard on `CONFIG_NET_UDP`
- `[mdnsd_daemon.c:CONFIG_NET_BROADCAST]` - Configuration guard on `CONFIG_NET_BROADCAST`
- `[mdnsd_event.c:CONFIG_NETLINK_ROUTE]` - Configuration guard on `CONFIG_NETLINK_ROUTE`

## Side Effects
- `[mdnsd_event.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[mdnsd_event.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[mdnsd_event.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[mdnsd_event.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
