# ltr308

## Overview
LTR308 ambient light sensor example (`ltr308`). Enable the LTR308 example

## Interface
- `[Kconfig:EXAMPLES_LTR308]` - Build configuration option `EXAMPLES_LTR308`
- `[Kconfig:EXAMPLES_LTR308_PROGNAME]` - Build configuration option `EXAMPLES_LTR308_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LTR308_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_LTR308_PROGNAME}`
- `[ltr308_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_LTR308]` - Requires kernel/app configuration `SENSORS_LTR308`

## Side Effects
- `[ltr308_main.c:/dev/uorb/sensor_light0]` - Opens or interacts with VFS/device path `/dev/uorb/sensor_light0`
- `[ltr308_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[ltr308_main.c:open]` - Opens device nodes or files via `open()`
- `[ltr308_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[ltr308_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
