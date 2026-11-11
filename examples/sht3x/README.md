# sht3x

## Overview
SHT3x sensor example (`sht3x`). Enable the SHT3x sensor example

## Interface
- `[Kconfig:EXAMPLES_SHT3X]` - Build configuration option `EXAMPLES_SHT3X`
- `[Kconfig:EXAMPLES_SHT3X_PROGNAME]` - Build configuration option `EXAMPLES_SHT3X_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SHT3X_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_SHT3X_PROGNAME}`
- `[sht3x_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_SHT3X]` - Requires kernel/app configuration `SENSORS_SHT3X`

## Side Effects
- `[sht3x_main.c:/dev/temp0]` - Opens or interacts with VFS/device path `/dev/temp0`
- `[sht3x_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[sht3x_main.c:open]` - Opens device nodes or files via `open()`
- `[sht3x_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
