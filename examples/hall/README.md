# hall

## Overview
Hall effect sensor example (`hall`). Enable the Hall effect sensor example

## Interface
- `[Kconfig:EXAMPLES_HALL]` - Build configuration option `EXAMPLES_HALL`
- `[Kconfig:EXAMPLES_HALL_DEVPATH]` - Build configuration option `EXAMPLES_HALL_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `hall`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `hall`
- `[hall.h:struct hall_example_s]` - Structure definition `hall_example_s`
- `[hall_main.c:decode_hall]` - Public function `decode_hall()`
- `[hall_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_HALL3PHASE]` - Requires kernel/app configuration `SENSORS_HALL3PHASE`
- `[hall_main.c:#error]` - Compile-time precondition: #endif
- `[hall_main.c:CONFIG_EXAMPLES_HALL_SENSOR_120DEG]` - Configuration guard on `CONFIG_EXAMPLES_HALL_SENSOR_120DEG`

## Side Effects
- `[hall_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[hall_main.c:open]` - Opens device nodes or files via `open()`
- `[hall_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
