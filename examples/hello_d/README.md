# hello_d

## Overview
"Hello, D!" D example (`hello_d`). Enable the "Hello, D!" D example

## Interface
- `[Kconfig:EXAMPLES_HELLO_D]` - Build configuration option `EXAMPLES_HELLO_D`
- `[Kconfig:EXAMPLES_HELLO_D_PROGNAME]` - Build configuration option `EXAMPLES_HELLO_D_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HELLO_D_PROGNAME)`

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
