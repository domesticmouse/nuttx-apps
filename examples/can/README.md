# can

## Overview
CAN example (`can`). Enable the CAN example

## Interface
- `[Kconfig:EXAMPLES_CAN]` - Build configuration option `EXAMPLES_CAN`
- `[Kconfig:EXAMPLES_CAN_DEVPATH]` - Build configuration option `EXAMPLES_CAN_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `can`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `can`
- `[can_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on CAN]` - Requires kernel/app configuration `CAN`
- `[can.h:#error]` - Compile-time precondition: CAN device support is not enabled (CONFIG_CAN)
- `[can.h:CONFIG_CAN]` - Configuration guard on `CONFIG_CAN`
- `[can_main.c:CONFIG_CAN_EXTID]` - Configuration guard on `CONFIG_CAN_EXTID`
- `[can_main.c:CONFIG_EXAMPLES_CAN_READ]` - Configuration guard on `CONFIG_EXAMPLES_CAN_READ`
- `[can_main.c:CONFIG_EXAMPLES_CAN_WRITE]` - Configuration guard on `CONFIG_EXAMPLES_CAN_WRITE`
- `[can_main.c:CONFIG_CAN_FD]` - Configuration guard on `CONFIG_CAN_FD`

## Side Effects
- `[can_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[can_main.c:open]` - Opens device nodes or files via `open()`
- `[can_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[can_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[can_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
