# cctype

## Overview
Verify C++ cctype operations (`cctype`). Enable the a simple test to verify C++ cctype operations.

## Interface
- `[Kconfig:EXAMPLES_CCTYPE]` - Build configuration option `EXAMPLES_CCTYPE`
- `[Makefile:PROGNAME]` - Registers application/module target `cctype`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `cctype`
- `[cctype_main.cxx:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[cctype_main.cxx:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
