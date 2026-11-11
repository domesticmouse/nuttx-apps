# lely_master

## Overview
Lely CANopen master example (`lely_master`). Enable the Lely CANopen master (comaster) example application.

## Interface
- `[Kconfig:EXAMPLES_LELYMASTER]` - Build configuration option `EXAMPLES_LELYMASTER`
- `[Kconfig:EXAMPLES_LELYMASTER_CHARDEV]` - Build configuration option `EXAMPLES_LELYMASTER_CHARDEV`
- `[Makefile:PROGNAME]` - Registers application/module target `comaster`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `comaster`
- `[candev.h:comaster_candev_init]` - Public function declaration `comaster_candev_init()`
- `[candev.h:comaster_candev_send]` - Public function declaration `comaster_candev_send()`
- `[candev.h:comaster_candev_recv]` - Public function declaration `comaster_candev_recv()`
- `[master_main.c:struct co_net_s]` - Structure definition `co_net_s`
- `[master_main.c:enum master_phase_e]` - Enumeration `master_phase_e`
- `[master_main.c:main]` - Application entry point `main()`
- `[candev_char.c:comaster_candev_init]` - Public function `comaster_candev_init()`
- `[candev_char.c:comaster_candev_send]` - Public function `comaster_candev_send()`
- `[candev_char.c:comaster_candev_recv]` - Public function `comaster_candev_recv()`
- `[candev_sock.c:comaster_candev_init]` - Public function `comaster_candev_init()`
- `[candev_sock.c:comaster_candev_send]` - Public function `comaster_candev_send()`
- `[candev_sock.c:comaster_candev_recv]` - Public function `comaster_candev_recv()`

## Invariants
- `[Kconfig:depends on CANUTILS_LELYCANOPEN && CANUTILS_LELYCANOPEN_SDEV]` - Requires kernel/app configuration `CANUTILS_LELYCANOPEN && CANUTILS_LELYCANOPEN_SDEV`
- `[Kconfig:depends on CANUTILS_LELYCANOPEN_TIME && CANUTILS_LELYCANOPEN_OBJUPLOAD]` - Requires kernel/app configuration `CANUTILS_LELYCANOPEN_TIME && CANUTILS_LELYCANOPEN_OBJUPLOAD`
- `[Kconfig:depends on CANUTILS_LELYCANOPEN_MASTER]` - Requires kernel/app configuration `CANUTILS_LELYCANOPEN_MASTER`
- `[candev_char.c:CONFIG_CAN_EXTID]` - Configuration guard on `CONFIG_CAN_EXTID`
- `[candev_char.c:CONFIG_CAN_ERRORS]` - Configuration guard on `CONFIG_CAN_ERRORS`

## Side Effects
- `[master_main.c:printf]` - Writes formatted output to standard output via `printf()`
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
