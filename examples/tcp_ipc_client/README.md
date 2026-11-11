# tcp_ipc_client

## Overview
Client for TCP IPC NuttX (`tcp_ipc_client`). Enable the Client for TCP IPC NuttX example

## Interface
- `[Kconfig:EXAMPLES_TCP_IPC_CLIENT]` - Build configuration option `EXAMPLES_TCP_IPC_CLIENT`
- `[Kconfig:EXAMPLES_TCP_IPC_CLIENT_PROGNAME]` - Build configuration option `EXAMPLES_TCP_IPC_CLIENT_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_TCP_IPC_CLIENT_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_TCP_IPC_CLIENT_PROGNAME}`
- `[protocol.h:send_msg_to_lpwan]` - Public function declaration `send_msg_to_lpwan()`
- `[tcp_ipc_client_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on EXAMPLES_TCP_IPC_CLIENT]` - Requires kernel/app configuration `EXAMPLES_TCP_IPC_CLIENT`
- `[Kconfig:depends on EXAMPLES_TCP_IPC_CLIENT]` - Requires kernel/app configuration `EXAMPLES_TCP_IPC_CLIENT`
- `[Kconfig:depends on EXAMPLES_TCP_IPC_CLIENT]` - Requires kernel/app configuration `EXAMPLES_TCP_IPC_CLIENT`
- `[tcp_ipc_client_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[tcp_ipc_client_main.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[tcp_ipc_client_main.c:connect]` - Connects sockets to remote peers via `connect()`
- `[tcp_ipc_client_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[tcp_ipc_client_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
