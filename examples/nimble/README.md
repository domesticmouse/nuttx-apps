# nimble

## Overview
NimBLE example (`nimble`). Enable the nimble example

## Interface
- `[Kconfig:EXAMPLES_NIMBLE]` - Build configuration option `EXAMPLES_NIMBLE`
- `[Kconfig:EXAMPLES_NIMBLE_PROGNAME]` - Build configuration option `EXAMPLES_NIMBLE_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NIMBLE_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `nimble`
- `[nimble_main.c:main]` - Application entry point `main()`

## Invariants
- `[nimble_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`
- `[nimble_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[nimble_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
