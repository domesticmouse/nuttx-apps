# bmp280

## Overview
BMP280 Barometer sensor example (`bmp280`). Enable the BMP280 example

## Interface
- `[Kconfig:EXAMPLES_BMP280]` - Build configuration option `EXAMPLES_BMP280`
- `[Kconfig:EXAMPLES_BMP280_PROGNAME]` - Build configuration option `EXAMPLES_BMP280_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_BMP280_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_BMP280_PROGNAME}`
- `[bmp280_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_BMP280]` - Requires kernel/app configuration `SENSORS_BMP280`

## Side Effects
- `[bmp280_main.c:/dev/uorb/sensor_baro0]` - Opens or interacts with VFS/device path `/dev/uorb/sensor_baro0`
- `[bmp280_main.c:open]` - Opens device nodes or files via `open()`
- `[bmp280_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[bmp280_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
