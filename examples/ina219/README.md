# ina219

## Overview
INA219 example (`ina219`). Enable the INA219 example

## Interface
- `[Kconfig:EXAMPLES_INA219]` - Build configuration option `EXAMPLES_INA219`
- `[Kconfig:EXAMPLES_INA219_PROGNAME]` - Build configuration option `EXAMPLES_INA219_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_INA219_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_INA219_PROGNAME}`
- `[ina219_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_INA219]` - Requires kernel/app configuration `SENSORS_INA219`

## Side Effects
- `[ina219_main.c:/dev/ina219]` - Opens or interacts with VFS/device path `/dev/ina219`
- `[ina219_main.c:open]` - Opens device nodes or files via `open()`
- `[ina219_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[ina219_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
