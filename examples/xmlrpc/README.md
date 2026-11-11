# xmlrpc

## Overview
XML RPC example (`xmlrpc`). An example for the netutils/xmlrpc library. This example implements a lightweight HTTP server and uses the xmlrpc lib for parsing xml remote procedure calls.

## Interface
- `[Kconfig:EXAMPLES_XMLRPC]` - Build configuration option `EXAMPLES_XMLRPC`
- `[Kconfig:EXAMPLES_XMLRPC_BUFFERSIZE]` - Build configuration option `EXAMPLES_XMLRPC_BUFFERSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `xmlrpc`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `xmlrpc`
- `[xmlrpc_main.c:main]` - Application entry point `main()`
- `[calls.c:calls_register]` - Public function `calls_register()`

## Invariants
- `[Kconfig:depends on NET_TCP]` - Requires kernel/app configuration `NET_TCP`
- `[Kconfig:depends on EXAMPLES_XMLRPC]` - Requires kernel/app configuration `EXAMPLES_XMLRPC`
- `[Kconfig:depends on EXAMPLES_XMLRPC && !NSH_NETINIT]` - Requires kernel/app configuration `EXAMPLES_XMLRPC && !NSH_NETINIT`
- `[xmlrpc_main.c:CONFIG_EXAMPLES_XMLRPC_DHCPC]` - Configuration guard on `CONFIG_EXAMPLES_XMLRPC_DHCPC`
- `[xmlrpc_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`
- `[xmlrpc_main.c:CONFIG_EXAMPLES_XMLRPC_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_XMLRPC_NOMAC`

## Side Effects
- `[xmlrpc_main.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[xmlrpc_main.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[xmlrpc_main.c:listen]` - Places sockets into passive listening state via `listen()`
- `[xmlrpc_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
