# serialblaster

## Overview
Serial Blaster example (`serialblaster`). Enable the serial blaster example

## Interface
- `[Kconfig:EXAMPLES_SERIALBLASTER]` - Build configuration option `EXAMPLES_SERIALBLASTER`
- `[Kconfig:EXAMPLES_SERIALBLASTER_STACKSIZE]` - Build configuration option `EXAMPLES_SERIALBLASTER_STACKSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `serialblaster`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `serialblaster`
- `[serialblaster_main.c:main]` - Application entry point `main()`

## Invariants
- `[serialblaster_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[serialblaster_main.c:open]` - Opens device nodes or files via `open()`
- `[serialblaster_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[serialblaster_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
