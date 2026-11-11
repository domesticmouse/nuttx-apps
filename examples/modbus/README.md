# modbus

## Overview
FreeModBus example (`modbus`). Enable the FreeModBus example

## Interface
- `[Kconfig:EXAMPLES_MODBUS]` - Build configuration option `EXAMPLES_MODBUS`
- `[Kconfig:EXAMPLES_MODBUS_PORT]` - Build configuration option `EXAMPLES_MODBUS_PORT`
- `[Makefile:PROGNAME]` - Registers application/module target `modbus`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `modbus`
- `[modbus_main.c:struct modbus_state_s]` - Structure definition `modbus_state_s`
- `[modbus_main.c:enum modbus_threadstate_e]` - Enumeration `modbus_threadstate_e`
- `[modbus_main.c:main]` - Application entry point `main()`
- `[modbus_main.c:eMBRegInputCB]` - Public function `eMBRegInputCB()`
- `[modbus_main.c:eMBRegHoldingCB]` - Public function `eMBRegHoldingCB()`
- `[modbus_main.c:eMBRegCoilsCB]` - Public function `eMBRegCoilsCB()`
- `[modbus_main.c:eMBRegDiscreteCB]` - Public function `eMBRegDiscreteCB()`
- `[modbus_main.c:getopt]` - Command-line option parser supporting flags `"desqh"`

## Invariants
- `[Kconfig:depends on USERLED]` - Requires kernel/app configuration `USERLED`
- `[modbus_main.c:CONFIG_EXAMPLES_MODBUS_REG_COILS_USERLEDS]` - Configuration guard on `CONFIG_EXAMPLES_MODBUS_REG_COILS_USERLEDS`
- `[modbus_main.c:CONFIG_EXAMPLES_MODBUS_PORT]` - Configuration guard on `CONFIG_EXAMPLES_MODBUS_PORT`
- `[modbus_main.c:CONFIG_EXAMPLES_MODBUS_BAUD]` - Configuration guard on `CONFIG_EXAMPLES_MODBUS_BAUD`
- `[modbus_main.c:CONFIG_EXAMPLES_MODBUS_PARITY]` - Configuration guard on `CONFIG_EXAMPLES_MODBUS_PARITY`

## Side Effects
- `[modbus_main.c:/dev/userleds]` - Opens or interacts with VFS/device path `/dev/userleds`
- `[modbus_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[modbus_main.c:open]` - Opens device nodes or files via `open()`
- `[modbus_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[modbus_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
