# discover

## Overview
UDP Discovery Example (`discover`). Enable the netutils/discover utility.  This example initializes and starts the UDP discover daemon. This daemon is useful for discovering devices in local networks, especially with DHCP configured devices.  It listens for UDP broadcasts which also can include a device class so that groups of devices can be discovered. It is also possible to address all classes with a kind of broadcast discover.

## Interface
- `[Kconfig:EXAMPLES_DISCOVER]` - Build configuration option `EXAMPLES_DISCOVER`
- `[Kconfig:EXAMPLES_DISCOVER_DHCPC]` - Build configuration option `EXAMPLES_DISCOVER_DHCPC`
- `[Makefile:PROGNAME]` - Registers application/module target `discover`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `discover`
- `[discover_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_UDP]` - Requires kernel/app configuration `NET_UDP`
- `[Kconfig:depends on EXAMPLES_DISCOVER && !NSH_NETINIT]` - Requires kernel/app configuration `EXAMPLES_DISCOVER && !NSH_NETINIT`
- `[Kconfig:depends on EXAMPLES_DISCOVER && !NSH_NETINIT]` - Requires kernel/app configuration `EXAMPLES_DISCOVER && !NSH_NETINIT`
- `[discover_main.c:CONFIG_EXAMPLES_DISCOVER_DHCPC]` - Configuration guard on `CONFIG_EXAMPLES_DISCOVER_DHCPC`
- `[discover_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`
- `[discover_main.c:CONFIG_EXAMPLES_DISCOVER_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_DISCOVER_NOMAC`

## Side Effects
- `[discover_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
