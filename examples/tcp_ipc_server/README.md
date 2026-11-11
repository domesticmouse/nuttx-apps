# tcp_ipc_server

## Overview
Server for TCP IPC NuttX (`tcp_ipc_server`). Enable the TCP SERVER example

## Interface
- `[Kconfig:EXAMPLES_TCP_IPC_SERVER]` - Build configuration option `EXAMPLES_TCP_IPC_SERVER`
- `[Kconfig:EXAMPLES_TCP_IPC_SERVER_PROGNAME]` - Build configuration option `EXAMPLES_TCP_IPC_SERVER_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_TCP_IPC_SERVER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_TCP_IPC_SERVER_PROGNAME}`
- `[protocol.h:send_msg_to_lpwan]` - Public function declaration `send_msg_to_lpwan()`
- `[tcp_ipc_server_main.c:main]` - Application entry point `main()`
- `[protocol.c:send_msg_to_lpwan]` - Public function `send_msg_to_lpwan()`
- `[uart_lorawan_layer.c:lorawan_radioenge_init]` - Public function `lorawan_radioenge_init()`
- `[uart_lorawan_layer.c:lorawan_radioenge_send_msg]` - Public function `lorawan_radioenge_send_msg()`
- **lorawan**: [`./lorawan/README.md`](./lorawan/README.md) - NuttX `tcp_ipc_server/lorawan` component implementing `uart_lorawan_layer.h`.

## Invariants
- `[Kconfig:depends on EXAMPLES_TCP_IPC_SERVER]` - Requires kernel/app configuration `EXAMPLES_TCP_IPC_SERVER`
- `[Kconfig:depends on EXAMPLES_TCP_IPC_SERVER]` - Requires kernel/app configuration `EXAMPLES_TCP_IPC_SERVER`
- `[Kconfig:depends on EXAMPLES_TCP_IPC_SERVER]` - Requires kernel/app configuration `EXAMPLES_TCP_IPC_SERVER`
- `[uart_lorawan_layer.c:#error]` - Compile-time precondition: CONFIG_ESP32_UART1 needs to be defined in order to compile this program.
- `[uart_lorawan_layer.c:CONFIG_ESP32_UART1]` - Configuration guard on `CONFIG_ESP32_UART1`

## Side Effects
- `[tcp_ipc_server_main.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[tcp_ipc_server_main.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[tcp_ipc_server_main.c:listen]` - Places sockets into passive listening state via `listen()`
- `[tcp_ipc_server_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[tcp_ipc_server_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[tcp_ipc_server_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[protocol.c:printf]` - Writes formatted output to standard output via `printf()`
- `[uart_lorawan_layer.c:/dev/ttyS1]` - Opens or interacts with VFS/device path `/dev/ttyS1`
- `[uart_lorawan_layer.c:open]` - Opens device nodes or files via `open()`
- `[uart_lorawan_layer.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[uart_lorawan_layer.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[uart_lorawan_layer.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
