# max31855

## Overview
"max31855" example (`max31855`). Enable the "max31855, World!" example

## Interface
- `[Kconfig:EXAMPLES_MAX31855]` - Build configuration option `EXAMPLES_MAX31855`
- `[Kconfig:EXAMPLES_MAX31855_PROGNAME]` - Build configuration option `EXAMPLES_MAX31855_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MAX31855_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MAX31855_PROGNAME}`
- `[max31855_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[max31855_main.c:/dev/temp0]` - Opens or interacts with VFS/device path `/dev/temp0`
- `[max31855_main.c:/dev/temp1]` - Opens or interacts with VFS/device path `/dev/temp1`
- `[max31855_main.c:/dev/temp2]` - Opens or interacts with VFS/device path `/dev/temp2`
- `[max31855_main.c:/dev/temp3]` - Opens or interacts with VFS/device path `/dev/temp3`
- `[max31855_main.c:open]` - Opens device nodes or files via `open()`
- `[max31855_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[max31855_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
