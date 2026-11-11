# lely_slave

## Overview
Lely CANopen slave example (`lely_slave`). Enable the Lely CANopen slave (coslave) example application.

## Interface
- `[Kconfig:EXAMPLES_LELYSLAVE]` - Build configuration option `EXAMPLES_LELYSLAVE`
- `[Kconfig:EXAMPLES_LELYSLAVE_CHARDEV]` - Build configuration option `EXAMPLES_LELYSLAVE_CHARDEV`
- `[Makefile:PROGNAME]` - Registers application/module target `coslave`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `coslave`
- `[candev.h:coslave_candev_init]` - Public function declaration `coslave_candev_init()`
- `[candev.h:coslave_candev_send]` - Public function declaration `coslave_candev_send()`
- `[candev.h:coslave_candev_recv]` - Public function declaration `coslave_candev_recv()`
- `[slave_main.c:struct co_net_s]` - Structure definition `co_net_s`
- `[slave_main.c:main]` - Application entry point `main()`
- `[candev_char.c:coslave_candev_init]` - Public function `coslave_candev_init()`
- `[candev_char.c:coslave_candev_send]` - Public function `coslave_candev_send()`
- `[candev_char.c:coslave_candev_recv]` - Public function `coslave_candev_recv()`
- `[candev_sock.c:coslave_candev_init]` - Public function `coslave_candev_init()`
- `[candev_sock.c:coslave_candev_send]` - Public function `coslave_candev_send()`
- `[candev_sock.c:coslave_candev_recv]` - Public function `coslave_candev_recv()`

## Invariants
- `[Kconfig:depends on CANUTILS_LELYCANOPEN && CANUTILS_LELYCANOPEN_SDEV]` - Requires kernel/app configuration `CANUTILS_LELYCANOPEN && CANUTILS_LELYCANOPEN_SDEV`
- `[Kconfig:depends on CANUTILS_LELYCANOPEN_TIME && CANUTILS_LELYCANOPEN_OBJUPLOAD]` - Requires kernel/app configuration `CANUTILS_LELYCANOPEN_TIME && CANUTILS_LELYCANOPEN_OBJUPLOAD`
- `[Kconfig:depends on CAN]` - Requires kernel/app configuration `CAN`
- `[candev_char.c:CONFIG_CAN_EXTID]` - Configuration guard on `CONFIG_CAN_EXTID`
- `[candev_char.c:CONFIG_CAN_ERRORS]` - Configuration guard on `CONFIG_CAN_ERRORS`

## Side Effects
- `[slave_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[candev_char.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[candev_char.c:open]` - Opens device nodes or files via `open()`
- `[candev_char.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[candev_char.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[candev_char.c:printf]` - Writes formatted output to standard output via `printf()`
- `[candev_sock.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[candev_sock.c:bind]` - Binds socket descriptors to local addresses via `bind()`
- `[candev_sock.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[candev_sock.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[candev_sock.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
