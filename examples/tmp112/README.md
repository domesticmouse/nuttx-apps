# tmp112

## Overview
TMP112 temperature sensor example (`tmp112`). Enable the TMP112 example

## Interface
- `[Kconfig:EXAMPLES_TMP112]` - Build configuration option `EXAMPLES_TMP112`
- `[Kconfig:EXAMPLES_TMP112_PROGNAME]` - Build configuration option `EXAMPLES_TMP112_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_TMP112_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_TMP112_PROGNAME}`
- `[tmp112_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_TMP112]` - Requires kernel/app configuration `SENSORS_TMP112`

## Side Effects
- `[tmp112_main.c:open]` - Opens device nodes or files via `open()`
- `[tmp112_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[tmp112_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
