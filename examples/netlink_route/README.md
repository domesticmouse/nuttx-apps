# netlink_route

## Overview
Netlink NETLINK_ROUTE test (`netlink_route`). Enable the Netlink NETLINK_ROUTE test

## Interface
- `[Kconfig:EXAMPLES_NETLINK_ROUTE]` - Build configuration option `EXAMPLES_NETLINK_ROUTE`
- `[Kconfig:EXAMPLES_NETLINK_ROUTE_PROGNAME]` - Build configuration option `EXAMPLES_NETLINK_ROUTE_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NETLINK_ROUTE_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NETLINK_ROUTE_PROGNAME}`
- `[netlink_route_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NETLINK_ROUTE]` - Requires kernel/app configuration `NETLINK_ROUTE`
- `[netlink_route_main.c:CONFIG_NETLINK_ROUTE]` - Configuration guard on `CONFIG_NETLINK_ROUTE`
- `[netlink_route_main.c:CONFIG_NET_IP]` - Configuration guard on `CONFIG_NET_IP`
- `[netlink_route_main.c:CONFIG_NETLINK_DISABLE_GETLINK]` - Configuration guard on `CONFIG_NETLINK_DISABLE_GETLINK`
- `[netlink_route_main.c:CONFIG_NETDEV_IFINDEX]` - Configuration guard on `CONFIG_NETDEV_IFINDEX`

## Side Effects
- `[netlink_route_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
