# ustream

## Overview
Unix domain stream example (`ustream`). Enable the Unix domain SOCK_STREAM test example

## Interface
- `[Kconfig:EXAMPLES_USTREAM]` - Build configuration option `EXAMPLES_USTREAM`
- `[Kconfig:EXAMPLES_USTREAM_ADDR]` - Build configuration option `EXAMPLES_USTREAM_ADDR`
- `[Makefile:PROGNAME]` - Registers application/module target `client server`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `client`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `server`
- `[ustream_client.c:main]` - Application entry point `main()`
- `[ustream_server.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_LOCAL]` - Requires kernel/app configuration `NET_LOCAL`
- `[ustream_client.c:CONFIG_EXAMPLES_USTREAM_USE_POLL]` - Configuration guard on `CONFIG_EXAMPLES_USTREAM_USE_POLL`
- `[ustream_server.c:CONFIG_EXAMPLES_USTREAM_USE_POLL]` - Configuration guard on `CONFIG_EXAMPLES_USTREAM_USE_POLL`

## Side Effects
- `[ustream_client.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[ustream_client.c:connect]` - Connects sockets to remote peers via `connect()`
- `[ustream_client.c:printf]` - Writes formatted output to standard output via `printf()`
- `[ustream_server.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[ustream_server.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[ustream_server.c:listen]` - Places sockets into passive listening state via `listen()`
- `[ustream_server.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
