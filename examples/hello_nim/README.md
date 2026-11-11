# hello_nim

## Overview
"Hello, Nim!" example (`hello_nim`). Enable the "Hello, Nim!" example in Nim language

## Interface
- `[Kconfig:EXAMPLES_HELLO_NIM]` - Build configuration option `EXAMPLES_HELLO_NIM`
- `[Kconfig:EXAMPLES_HELLO_NIM_PROGNAME]` - Build configuration option `EXAMPLES_HELLO_NIM_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HELLO_NIM_PROGNAME)`
- `[hello_nim_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
