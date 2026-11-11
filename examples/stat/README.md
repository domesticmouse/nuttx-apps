# stat

## Overview
Test of stat(), fstat(), and statfs() (`stat`). Enable the test of stat(), fstat(), and statfs().

## Interface
- `[Kconfig:EXAMPLES_STAT]` - Build configuration option `EXAMPLES_STAT`
- `[Kconfig:EXAMPLES_STAT_PROGNAME]` - Build configuration option `EXAMPLES_STAT_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_STAT_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_STAT_PROGNAME}`
- `[stat_main.c:main]` - Application entry point `main()`

## Invariants
- `[stat_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[stat_main.c:open]` - Opens device nodes or files via `open()`
- `[stat_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
