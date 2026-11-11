# ini_dumper

## Overview
ini dumper example (`ini_dumper`). Enable ini dumper example program which uses inih

## Interface
- `[Kconfig:EXAMPLES_INI_DUMPER]` - Build configuration option `EXAMPLES_INI_DUMPER`
- `[Kconfig:EXAMPLES_INI_DUMPER_PROGNAME]` - Build configuration option `EXAMPLES_INI_DUMPER_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_INI_DUMPER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_INI_DUMPER_PROGNAME}`
- `[ini_dumper_main.c:main]` - Application entry point `main()`

## Invariants
- `[ini_dumper_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[ini_dumper_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
