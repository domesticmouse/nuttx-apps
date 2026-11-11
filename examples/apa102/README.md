# apa102

## Overview
APA102 LED Strip example (`apa102`). Enable the APA102 example

## Interface
- `[Kconfig:EXAMPLES_APA102]` - Build configuration option `EXAMPLES_APA102`
- `[Kconfig:EXAMPLES_APA102_PROGNAME]` - Build configuration option `EXAMPLES_APA102_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_APA102_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_APA102_PROGNAME}`
- `[apa102_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on LEDS_APA102]` - Requires kernel/app configuration `LEDS_APA102`

## Side Effects
- `[apa102_main.c:/dev/leddrv0]` - Opens or interacts with VFS/device path `/dev/leddrv0`
- `[apa102_main.c:open]` - Opens device nodes or files via `open()`
- `[apa102_main.c:write]` - Writes bytes to file or device descriptors via `write()`

## Verification
- Run: `make test`
