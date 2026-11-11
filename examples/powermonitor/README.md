# powermonitor

## Overview
LTC4151 powermonitor example (`powermonitor`).

## Interface
- `[Kconfig:EXAMPLES_POWERMONITOR]` - Build configuration option `EXAMPLES_POWERMONITOR`
- `[Makefile:PROGNAME]` - Registers application/module target `powermonitor`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `powermonitor`
- `[powermonitor_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_LTC4151]` - Requires kernel/app configuration `SENSORS_LTC4151`
- `[powermonitor_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[powermonitor_main.c:/dev/pwrmntr0]` - Opens or interacts with VFS/device path `/dev/pwrmntr0`
- `[powermonitor_main.c:open]` - Opens device nodes or files via `open()`
- `[powermonitor_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[powermonitor_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
