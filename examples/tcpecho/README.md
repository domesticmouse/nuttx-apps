# tcpecho

## Overview
Simple TCP echo server (`tcpecho`). Simple single threaded, poll based TCP echo server. This example implements the TCP Echo Server from W. Richard Stevens UNIX Network Programming Book.

## Interface
- `[Kconfig:EXAMPLES_TCPECHO]` - Build configuration option `EXAMPLES_TCPECHO`
- `[Kconfig:EXAMPLES_TCPECHO_PORT]` - Build configuration option `EXAMPLES_TCPECHO_PORT`
- `[Makefile:PROGNAME]` - Registers application/module target `tcpecho`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `tcpecho`
- `[tcpecho_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on EXAMPLES_TCPECHO]` - Requires kernel/app configuration `EXAMPLES_TCPECHO`
- `[Kconfig:depends on EXAMPLES_TCPECHO]` - Requires kernel/app configuration `EXAMPLES_TCPECHO`
- `[Kconfig:depends on EXAMPLES_TCPECHO]` - Requires kernel/app configuration `EXAMPLES_TCPECHO`
- `[tcpecho_main.c:CONFIG_EXAMPLES_TCPECHO_DHCPC]` - Configuration guard on `CONFIG_EXAMPLES_TCPECHO_DHCPC`
- `[tcpecho_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`
- `[tcpecho_main.c:CONFIG_EXAMPLES_TCPECHO_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_TCPECHO_NOMAC`

## Side Effects
- `[tcpecho_main.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[tcpecho_main.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[tcpecho_main.c:listen]` - Places sockets into passive listening state via `listen()`
- `[tcpecho_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[tcpecho_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
