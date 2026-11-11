# nanoxcalc

## Overview
Nano-X calculator example (`nanoxcalc`). Enable the Nano-X calculator example application.  It is a port of the nxcalc demo from Microwindows which connects to the Nano-X server started by examples/nanoxterm and shows a calculator keypad operated by the mouse or keyboard.

## Interface
- `[Kconfig:EXAMPLES_NANOXCALC]` - Build configuration option `EXAMPLES_NANOXCALC`
- `[Kconfig:EXAMPLES_NANOXCALC_PROGNAME]` - Build configuration option `EXAMPLES_NANOXCALC_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NANOXCALC_PROGNAME)`
- `[nxcalc.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on MICROWINDOWS_NANOX && LIBC_FLOATINGPOINT]` - Requires kernel/app configuration `MICROWINDOWS_NANOX && LIBC_FLOATINGPOINT`

## Side Effects
- None

## Verification
- Run: `make test`
