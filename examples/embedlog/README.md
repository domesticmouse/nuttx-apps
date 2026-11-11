# embedlog

## Overview
embedlog example (`embedlog`). Enable the "embedlog" example.

## Interface
- `[Kconfig:EXAMPLES_EMBEDLOG]` - Build configuration option `EXAMPLES_EMBEDLOG`
- `[Kconfig:EXAMPLES_EMBEDLOG_STRIP_ALL_STRINGS]` - Build configuration option `EXAMPLES_EMBEDLOG_STRIP_ALL_STRINGS`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_EMBEDLOG_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_EMBEDLOG_PROGNAME}`
- `[embedlog_main.c:main]` - Application entry point `main()`

## Invariants
- `[embedlog_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- None

## Verification
- Run: `make test`
