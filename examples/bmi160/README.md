# bmi160

## Overview
BMI160 sensor example (`bmi160`). Enable the 6 axis sensor example

## Interface
- `[Kconfig:EXAMPLES_SIXAXIS]` - Build configuration option `EXAMPLES_SIXAXIS`
- `[Kconfig:EXAMPLES_SIXAXIS_UORB]` - Build configuration option `EXAMPLES_SIXAXIS_UORB`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SIXAXIS_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_SIXAXIS_PROGNAME}`
- `[sixaxis_main.c:main]` - Application entry point `main()`
- `[sixaxis_uorb_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_BMI160]` - Requires kernel/app configuration `SENSORS_BMI160`
- `[Kconfig:depends on SENSORS_BMI160_UORB]` - Requires kernel/app configuration `SENSORS_BMI160_UORB`
- `[sixaxis_uorb_main.c:CONFIG_DEBUG_UORB]` - Configuration guard on `CONFIG_DEBUG_UORB`

## Side Effects
- `[sixaxis_main.c:/dev/accel0]` - Opens or interacts with VFS/device path `/dev/accel0`
- `[sixaxis_main.c:open]` - Opens device nodes or files via `open()`
- `[sixaxis_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[sixaxis_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[sixaxis_uorb_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
