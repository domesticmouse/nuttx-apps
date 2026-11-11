# bmp180

## Overview
BMP180 Barometer sensor example (`bmp180`). Enable the BMP180 example

## Interface
- `[Kconfig:EXAMPLES_BMP180]` - Build configuration option `EXAMPLES_BMP180`
- `[Kconfig:EXAMPLES_BMP180_PROGNAME]` - Build configuration option `EXAMPLES_BMP180_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_BMP180_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_BMP180_PROGNAME}`
- `[bmp180_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_BMP180]` - Requires kernel/app configuration `SENSORS_BMP180`

## Side Effects
- `[bmp180_main.c:/dev/press0]` - Opens or interacts with VFS/device path `/dev/press0`
- `[bmp180_main.c:open]` - Opens device nodes or files via `open()`
- `[bmp180_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[bmp180_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
