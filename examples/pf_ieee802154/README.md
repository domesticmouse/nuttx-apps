# pf_ieee802154

## Overview
PF_IEEE802154 example (`pf_ieee802154`). Enable the PF_IEEE802154 socket example

## Interface
- `[Kconfig:EXAMPLES_PFIEEE802154]` - Build configuration option `EXAMPLES_PFIEEE802154`
- `[Kconfig:EXAMPLES_PFIEEE802154_PROGNAME1]` - Build configuration option `EXAMPLES_PFIEEE802154_PROGNAME1`
- `[Makefile:PROGNAME]` - Registers application/module target `pfserver pfclient`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `pfserver`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `pfclient`
- `[pfieee802154.h:pf_cmdline]` - Public function declaration `pf_cmdline()`
- `[pfieee802154.h:pf_client]` - Public function declaration `pf_client()`
- `[pfieee802154.h:pf_server]` - Public function declaration `pf_server()`
- `[pf_client.c:main]` - Application entry point `main()`
- `[pf_cmdline.c:pf_cmdline]` - Public function `pf_cmdline()`
- `[pf_server.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_IEEE802154]` - Requires kernel/app configuration `NET_IEEE802154`
- `[pf_cmdline.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[pf_client.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[pf_client.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[pf_client.c:sendto]` - Sends datagram packets via `sendto()`
- `[pf_client.c:printf]` - Writes formatted output to standard output via `printf()`
- `[pf_server.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[pf_server.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[pf_server.c:recvfrom]` - Receives datagram packets via `recvfrom()`
- `[pf_server.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
