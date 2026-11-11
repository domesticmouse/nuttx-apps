# scd41

## Overview
SCD41 CO2 sensor example (`scd41`). Enable the SCD41 CO2 sensor example

## Interface
- `[Kconfig:EXAMPLES_SCD41]` - Build configuration option `EXAMPLES_SCD41`
- `[Kconfig:EXAMPLES_SCD41_PROGNAME]` - Build configuration option `EXAMPLES_SCD41_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SCD41_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_SCD41_PROGNAME}`
- `[scd41_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_SCD41]` - Requires kernel/app configuration `SENSORS_SCD41`

## Side Effects
- `[scd41_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[scd41_main.c:open]` - Opens device nodes or files via `open()`
- `[scd41_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
