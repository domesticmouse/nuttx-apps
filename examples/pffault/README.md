# pffault

## Overview
Page-fault / PMS isolation test (`pffault`). A user-space task that deliberately touches a kernel-space address to exercise the ESP32-S3 PMS isolation boundary and the kernel's recoverable-fault dispatcher.

## Interface
- `[Kconfig:EXAMPLES_PFFAULT]` - Build configuration option `EXAMPLES_PFFAULT`
- `[Kconfig:EXAMPLES_PFFAULT_PROGNAME]` - Build configuration option `EXAMPLES_PFFAULT_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_PFFAULT_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_PFFAULT_PROGNAME}`
- `[pffault_main.c:main]` - Application entry point `main()`

## Invariants
- `[pffault_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[pffault_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
