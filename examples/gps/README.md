# gps

## Overview
GPS example (`gps`). Enable the gps test example

## Interface
- `[Kconfig:EXAMPLES_GPS]` - Build configuration option `EXAMPLES_GPS`
- `[Kconfig:EXAMPLES_GPS_PROGNAME]` - Build configuration option `EXAMPLES_GPS_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_GPS_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_GPS_PROGNAME}`
- `[gps_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on GNSSUTILS_MINMEA_LIB]` - Requires kernel/app configuration `GNSSUTILS_MINMEA_LIB`
- `[gps_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[gps_main.c:/dev/ttyS1]` - Opens or interacts with VFS/device path `/dev/ttyS1`
- `[gps_main.c:open]` - Opens device nodes or files via `open()`
- `[gps_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[gps_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
