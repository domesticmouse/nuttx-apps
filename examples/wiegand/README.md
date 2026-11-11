# wiegand

## Overview
Wiegand example (`wiegand`). Enable the wiegand example

## Interface
- `[Kconfig:EXAMPLES_WIEGAND]` - Build configuration option `EXAMPLES_WIEGAND`
- `[Kconfig:EXAMPLES_WIEGAND_PROGNAME]` - Build configuration option `EXAMPLES_WIEGAND_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_WIEGAND_PROGNAME)`
- `[wiegand.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[wiegand.c:/dev/wiega0]` - Opens or interacts with VFS/device path `/dev/wiega0`
- `[wiegand.c:open]` - Opens device nodes or files via `open()`
- `[wiegand.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[wiegand.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
