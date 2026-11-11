# hello_zig

## Overview
"Hello, Zig!" example (`hello_zig`). Enable the "Hello, Zig!" example

## Interface
- `[Kconfig:EXAMPLES_HELLO_ZIG]` - Build configuration option `EXAMPLES_HELLO_ZIG`
- `[Kconfig:EXAMPLES_HELLO_ZIG_PROGNAME]` - Build configuration option `EXAMPLES_HELLO_ZIG_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HELLO_ZIG_PROGNAME)`
- `[hello_zig.zig:struct NuttX]` - Zig namespace/struct `NuttX`

## Invariants
- None

## Side Effects
- `[hello_zig.zig:printf]` - Outputs status messages via C `printf()`

## Verification
- Run: `make test`
