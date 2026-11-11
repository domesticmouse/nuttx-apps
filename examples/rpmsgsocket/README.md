# rpmsgsocket

## Overview
Rpmsg socket example (`rpmsgsocket`). Enable the rpmsg socket test example

## Interface
- `[Kconfig:EXAMPLES_RPMSGSOCKET]` - Build configuration option `EXAMPLES_RPMSGSOCKET`
- `[Makefile:PROGNAME]` - Registers application/module target `rpsock_client rpsock_server`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `rpsock_client`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `rpsock_server`
- `[rpsock_client.c:struct rpsock_arg_s]` - Structure definition `rpsock_arg_s`
- `[rpsock_client.c:main]` - Application entry point `main()`
- `[rpsock_server.c:struct rpsock_arg_s]` - Structure definition `rpsock_arg_s`
- `[rpsock_server.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_RPMSG]` - Requires kernel/app configuration `NET_RPMSG`
- `[rpsock_client.c:argc]` - Validates command-line argument count `argc`
- `[rpsock_server.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[rpsock_client.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[rpsock_client.c:connect]` - Connects sockets to remote peers via `connect()`
- `[rpsock_client.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[rpsock_client.c:printf]` - Writes formatted output to standard output via `printf()`
- `[rpsock_server.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[rpsock_server.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[rpsock_server.c:connect]` - Connects sockets to remote peers via `connect()`
- `[rpsock_server.c:listen]` - Places sockets into passive listening state via `listen()`
- `[rpsock_server.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[rpsock_server.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
