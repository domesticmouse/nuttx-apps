# isl29023

## Overview
ISL29023 driver example (`isl29023`). Enable the example application

## Interface
- `[Kconfig:EXAMPLES_ISL29023]` - Build configuration option `EXAMPLES_ISL29023`
- `[Makefile:PROGNAME]` - Registers application/module target `isl29023`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `isl29023`
- `[isl29023_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_ISL29023]` - Requires kernel/app configuration `SENSORS_ISL29023`

## Side Effects
- `[isl29023_main.c:/dev/als0]` - Opens or interacts with VFS/device path `/dev/als0`
- `[isl29023_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[isl29023_main.c:open]` - Opens device nodes or files via `open()`
- `[isl29023_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[isl29023_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
