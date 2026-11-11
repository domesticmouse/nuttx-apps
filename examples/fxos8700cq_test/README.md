# fxos8700cq_test

## Overview
FXOS8700CQ motion sensor example (`fxos8700cq_test`). Enable the motion sensor example

## Interface
- `[Kconfig:EXAMPLES_FXOS8700CQ]` - Build configuration option `EXAMPLES_FXOS8700CQ`
- `[Kconfig:EXAMPLES_FXOS8700CQ_PROGNAME]` - Build configuration option `EXAMPLES_FXOS8700CQ_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_FXOS8700CQ_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_FXOS8700CQ_PROGNAME}`
- `[fxos8700cq_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[fxos8700cq_main.c:/dev/accel0]` - Opens or interacts with VFS/device path `/dev/accel0`
- `[fxos8700cq_main.c:open]` - Opens device nodes or files via `open()`
- `[fxos8700cq_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[fxos8700cq_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
