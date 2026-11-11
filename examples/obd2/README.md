# obd2

## Overview
OBD-II application example (`obd2`). Enable the OBD-II application example.

## Interface
- `[Kconfig:EXAMPLES_OBD2]` - Build configuration option `EXAMPLES_OBD2`
- `[Makefile:PROGNAME]` - Registers application/module target `obd2`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `obd2`
- `[obd2_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[obd2_main.c:/dev/can0]` - Opens or interacts with VFS/device path `/dev/can0`
- `[obd2_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
