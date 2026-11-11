# leds_zig

## Overview
"LEDs Zig" example (`leds_zig`). Enable the "LEDs Zig" example

## Interface
- `[Kconfig:EXAMPLES_LEDS_ZIG]` - Build configuration option `EXAMPLES_LEDS_ZIG`
- `[Kconfig:EXAMPLES_LEDS_ZIG_PROGNAME]` - Build configuration option `EXAMPLES_LEDS_ZIG_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LEDS_ZIG_PROGNAME)`
- `[leds_zig.zig:struct NuttX]` - Zig namespace/struct `NuttX`

## Invariants
- `[Kconfig:depends on USERLED]` - Requires kernel/app configuration `USERLED`

## Side Effects
- `[leds_zig.zig:ioctl]` - Performs LED driver `ioctl` calls via C ABI
- `[leds_zig.zig:printf]` - Outputs status messages via C `printf()`

## Verification
- Run: `make test`
