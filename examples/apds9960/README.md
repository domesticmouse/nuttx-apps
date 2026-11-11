# apds9960

## Overview
APDS-9960 Test Application (`apds9960`). Enable the APDS-9960 test application.

## Interface
- `[Kconfig:EXAMPLES_APDS9960]` - Build configuration option `EXAMPLES_APDS9960`
- `[Kconfig:EXAMPLES_APDS9960_PROGNAME]` - Build configuration option `EXAMPLES_APDS9960_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_APDS9960_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_APDS9960_PROGNAME}`
- `[apds9960_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_APDS9960]` - Requires kernel/app configuration `SENSORS_APDS9960`
- `[apds9960_main.c:CONFIG_EXAMPLES_APDS9960_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_APDS9960_DEVNAME`

## Side Effects
- `[apds9960_main.c:/dev/gest0]` - Opens or interacts with VFS/device path `/dev/gest0`
- `[apds9960_main.c:open]` - Opens device nodes or files via `open()`
- `[apds9960_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[apds9960_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
