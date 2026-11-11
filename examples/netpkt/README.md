# netpkt

## Overview
Network packet socket example (`netpkt`). Enable the network packet socket example

## Interface
- `[Kconfig:EXAMPLES_NETPKT]` - Build configuration option `EXAMPLES_NETPKT`
- `[Makefile:PROGNAME]` - Registers application/module target `netpkt netpkt_ethercat`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `netpkt`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `netpkt_ethercat`
- `[netpkt_main.c:main]` - Application entry point `main()`
- `[netpkt_main.c:getopt]` - Command-line option parser supporting flags `"artvi:"`
- `[netpkt_ethercat.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_PKT]` - Requires kernel/app configuration `NET_PKT`
- `[netpkt_main.c:argc]` - Validates command-line argument count `argc`
- `[netpkt_ethercat.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[netpkt_main.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[netpkt_main.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[netpkt_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[netpkt_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[netpkt_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[netpkt_ethercat.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[netpkt_ethercat.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[netpkt_ethercat.c:sendto]` - Sends datagram packets via `sendto()`
- `[netpkt_ethercat.c:recvfrom]` - Receives datagram packets via `recvfrom()`
- `[netpkt_ethercat.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
