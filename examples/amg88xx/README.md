# amg88xx

## Overview
AMG88xx sensor example (`amg88xx`). Enable the AMG88xx sensor example

## Interface
- `[Kconfig:EXAMPLES_AMG88XX]` - Build configuration option `EXAMPLES_AMG88XX`
- `[Kconfig:EXAMPLES_AMG88XX_PROGNAME]` - Build configuration option `EXAMPLES_AMG88XX_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_AMG88XX_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_AMG88XX_PROGNAME}`
- `[amg88xx_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_AMG88XX]` - Requires kernel/app configuration `SENSORS_AMG88XX`

## Side Effects
- `[amg88xx_main.c:/dev/irm0]` - Opens or interacts with VFS/device path `/dev/irm0`
- `[amg88xx_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[amg88xx_main.c:open]` - Opens device nodes or files via `open()`
- `[amg88xx_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[amg88xx_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
