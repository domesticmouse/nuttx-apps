# cbortest

## Overview
TinyCBOR Test Example (`cbortest`). Enable the TinyCBOR test example

## Interface
- `[Kconfig:EXAMPLES_TINYCBOR_TEST]` - Build configuration option `EXAMPLES_TINYCBOR_TEST`
- `[Kconfig:EXAMPLES_TINYCBOR_TEST_PROGNAME]` - Build configuration option `EXAMPLES_TINYCBOR_TEST_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_TINYCBOR_TEST_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_TINYCBOR_TEST_PROGNAME}`
- `[cbortest_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on FSUTILS_TINYCBOR_LIB]` - Requires kernel/app configuration `FSUTILS_TINYCBOR_LIB`

## Side Effects
- `[cbortest_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
