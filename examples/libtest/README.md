# libtest

## Overview
Static library Example (`libtest`). Enable the static library example

## Interface
- `[Kconfig:EXAMPLES_LIBTEST]` - Build configuration option `EXAMPLES_LIBTEST`
- `[Kconfig:EXAMPLES_LIBTEST_CMDTOOL]` - Build configuration option `EXAMPLES_LIBTEST_CMDTOOL`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LIBTEST_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_LIBTEST_PROGNAME}`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `libtest`
- `[libtest.h:library_test]` - Public function declaration `library_test()`
- `[libtest.c:library_test]` - Public function `library_test()`
- `[libtest_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[libtest.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
