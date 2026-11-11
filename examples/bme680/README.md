# bme680

## Overview
BME680 sensor example (`bme680`). Enable the BME680 example

## Interface
- `[Kconfig:EXAMPLES_BME680]` - Build configuration option `EXAMPLES_BME680`
- `[Kconfig:EXAMPLES_BME680_PROGNAME]` - Build configuration option `EXAMPLES_BME680_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_BME680_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_BME680_PROGNAME}`
- `[bme680_main.c:struct data]` - Structure definition `data`
- `[bme680_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_BME680]` - Requires kernel/app configuration `SENSORS_BME680`

## Side Effects
- `[bme680_main.c:/dev/uorb/sensor_baro0]` - Opens or interacts with VFS/device path `/dev/uorb/sensor_baro0`
- `[bme680_main.c:/dev/uorb/sensor_gas0]` - Opens or interacts with VFS/device path `/dev/uorb/sensor_gas0`
- `[bme680_main.c:/dev/uorb/sensor_humi0]` - Opens or interacts with VFS/device path `/dev/uorb/sensor_humi0`
- `[bme680_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[bme680_main.c:open]` - Opens device nodes or files via `open()`
- `[bme680_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[bme680_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
