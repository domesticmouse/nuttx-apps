# dhtxx

## Overview
Dhtxx sensor example (`dhtxx`). Enable the dhtxx sensor example

## Interface
- `[Kconfig:EXAMPLES_DHTXX]` - Build configuration option `EXAMPLES_DHTXX`
- `[Kconfig:EXAMPLES_DHTXX_PROGNAME]` - Build configuration option `EXAMPLES_DHTXX_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_DHTXX_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_DHTXX_PROGNAME}`
- `[dhtxx_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_DHTXX]` - Requires kernel/app configuration `SENSORS_DHTXX`

## Side Effects
- `[dhtxx_main.c:open]` - Opens device nodes or files via `open()`
- `[dhtxx_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[dhtxx_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
