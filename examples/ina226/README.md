# ina226

## Overview
INA226 example (`ina226`). Enable the INA226 example

## Interface
- `[Kconfig:EXAMPLES_INA226]` - Build configuration option `EXAMPLES_INA226`
- `[Kconfig:EXAMPLES_INA226_PROGNAME]` - Build configuration option `EXAMPLES_INA226_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_INA226_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `ina226`
- `[ina226_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_INA226]` - Requires kernel/app configuration `SENSORS_INA226`
- `[ina226_main.c:CONFIG_INA226_DEVICE_PATH]` - Configuration guard on `CONFIG_INA226_DEVICE_PATH`

## Side Effects
- `[ina226_main.c:/dev/ina226]` - Opens or interacts with VFS/device path `/dev/ina226`
- `[ina226_main.c:open]` - Opens device nodes or files via `open()`
- `[ina226_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[ina226_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
