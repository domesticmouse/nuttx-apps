# rgbled

## Overview
RGB LED Test (`rgbled`). Enable the RGB LED example

## Interface
- `[Kconfig:EXAMPLES_RGBLED]` - Build configuration option `EXAMPLES_RGBLED`
- `[Kconfig:EXAMPLES_RGBLED_DEVNAME]` - Build configuration option `EXAMPLES_RGBLED_DEVNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_RGBLED_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_RGBLED_PROGNAME}`
- `[rgbled.c:main]` - Application entry point `main()`

## Invariants
- `[rgbled.c:CONFIG_EXAMPLES_RGBLED_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_RGBLED_DEVNAME`

## Side Effects
- `[rgbled.c:/dev/rgbled0]` - Opens or interacts with VFS/device path `/dev/rgbled0`
- `[rgbled.c:open]` - Opens device nodes or files via `open()`
- `[rgbled.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[rgbled.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
