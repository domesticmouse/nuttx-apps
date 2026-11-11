# udgram

## Overview
Unix domain datagram example (`udgram`). Enable the Unix domain SOCK_DGRAM test example

## Interface
- `[Kconfig:EXAMPLES_UDGRAM]` - Build configuration option `EXAMPLES_UDGRAM`
- `[Kconfig:EXAMPLES_UDGRAM_ADDR]` - Build configuration option `EXAMPLES_UDGRAM_ADDR`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_UDGRAM_CLIENT_PROGNAME)`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_UDGRAM_SERVER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_UDGRAM_CLIENT_PROGNAME}`
- `[udgram_client.c:main]` - Application entry point `main()`
- `[udgram_server.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_LOCAL]` - Requires kernel/app configuration `NET_LOCAL`

## Side Effects
- `[udgram_client.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[udgram_client.c:sendto]` - Sends datagram packets via `sendto()`
- `[udgram_client.c:printf]` - Writes formatted output to standard output via `printf()`
- `[udgram_server.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[udgram_server.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[udgram_server.c:recvfrom]` - Receives datagram packets via `recvfrom()`
- `[udgram_server.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
