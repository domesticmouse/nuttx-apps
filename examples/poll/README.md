# poll

## Overview
Poll example (`poll`). Enable the poll example

## Interface
- `[Kconfig:EXAMPLES_POLL]` - Build configuration option `EXAMPLES_POLL`
- `[Kconfig:EXAMPLES_POLL_NOMAC]` - Build configuration option `EXAMPLES_POLL_NOMAC`
- `[Makefile:PROGNAME]` - Registers application/module target `poll`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `poll`
- `[poll_internal.h:poll_listener]` - Public function declaration `poll_listener()`
- `[poll_internal.h:select_listener]` - Public function declaration `select_listener()`
- `[poll_internal.h:net_listener]` - Public function declaration `net_listener()`
- `[poll_internal.h:net_reader]` - Public function declaration `net_reader()`
- `[poll_main.c:main]` - Application entry point `main()`
- `[host.c:main]` - Application entry point `main()`
- `[net_listener.c:struct net_listener_s]` - Structure definition `net_listener_s`
- `[net_listener.c:net_listener]` - Public function `net_listener()`
- `[net_reader.c:net_reader]` - Public function `net_reader()`
- `[poll_listener.c:poll_listener]` - Public function `poll_listener()`
- `[select_listener.c:select_listener]` - Public function `select_listener()`

## Invariants
- `[Kconfig:depends on PIPES]` - Requires kernel/app configuration `PIPES`
- `[poll_internal.h:CONFIG_NET]` - Configuration guard on `CONFIG_NET`
- `[poll_main.c:CONFIG_NET_TCPBACKLOG]` - Configuration guard on `CONFIG_NET_TCPBACKLOG`
- `[host.c:#error]` - Compile-time precondition: TARGETIP not defined
- `[net_listener.c:CONFIG_EXAMPLES_POLL_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_POLL_NOMAC`
- `[net_reader.c:CONFIG_EXAMPLES_POLL_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_POLL_NOMAC`
- `[poll_listener.c:CONFIG_DEV_CONSOLE]` - Configuration guard on `CONFIG_DEV_CONSOLE`

## Side Effects
- `[poll_internal.h:/dev/fifo0]` - Opens or interacts with VFS/device path `/dev/fifo0`
- `[poll_internal.h:/dev/fifo1]` - Opens or interacts with VFS/device path `/dev/fifo1`
- `[poll_main.c:open]` - Opens device nodes or files via `open()`
- `[poll_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[poll_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[poll_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[host.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[host.c:connect]` - Connects sockets to remote peers via `connect()`
- `[host.c:printf]` - Writes formatted output to standard output via `printf()`
- `[net_listener.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[net_listener.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[net_listener.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[net_listener.c:listen]` - Places sockets into passive listening state via `listen()`
- `[net_listener.c:printf]` - Writes formatted output to standard output via `printf()`
- `[net_reader.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[net_reader.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[net_reader.c:listen]` - Places sockets into passive listening state via `listen()`
- `[net_reader.c:printf]` - Writes formatted output to standard output via `printf()`
- `[poll_listener.c:open]` - Opens device nodes or files via `open()`
- `[poll_listener.c:read]` - Reads bytes from file or device descriptors via `read()`

## Verification
- Run: `make test`
