# slot_confirm

## Overview
MCUboot slot confirm example (`mcuboot/slot_confirm`). Example application for confirming a newly installed application application firmware image using MCUboot public APIs. This application should be used as the OTA update package of the EXAMPLES_MCUBOOT_UPDATE_AGENT example.

## Interface
- `[Kconfig:EXAMPLES_MCUBOOT_SLOT_CONFIRM]` - Build configuration option `EXAMPLES_MCUBOOT_SLOT_CONFIRM`
- `[Makefile:PROGNAME]` - Registers application/module target `mcuboot_confirm`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `mcuboot_confirm2`
- `[mcuboot_confirm_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[mcuboot_confirm_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
