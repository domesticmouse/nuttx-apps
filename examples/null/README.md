# null

## Overview
NULL example (`null`). Enable the NULL example

## Interface
- `[Kconfig:EXAMPLES_NULL]` - Build configuration option `EXAMPLES_NULL`
- `[Makefile:PROGNAME]` - Registers application/module target `null`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `null`
- `[null_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
