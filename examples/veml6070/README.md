# veml6070

## Overview
VEML6070 UltraViolet sensor example (`veml6070`). Enable the VEML6070 example

## Interface
- `[Kconfig:EXAMPLES_VEML6070]` - Build configuration option `EXAMPLES_VEML6070`
- `[Kconfig:EXAMPLES_VEML6070_PROGNAME]` - Build configuration option `EXAMPLES_VEML6070_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_VEML6070_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_VEML6070_PROGNAME}`
- `[veml6070_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_VEML6070]` - Requires kernel/app configuration `SENSORS_VEML6070`

## Side Effects
- `[veml6070_main.c:/dev/uvlight0]` - Opens or interacts with VFS/device path `/dev/uvlight0`
- `[veml6070_main.c:open]` - Opens device nodes or files via `open()`
- `[veml6070_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[veml6070_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
