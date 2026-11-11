# nimble_bleess

## Overview
NimBLE Environmental Sensing peripheral (`nimble_bleess`). Enable the NimBLE Environmental Sensing peripheral example.

## Interface
- `[Kconfig:EXAMPLES_NIMBLE_BLEESS]` - Build configuration option `EXAMPLES_NIMBLE_BLEESS`
- `[Kconfig:EXAMPLES_NIMBLE_BLEESS_PROGNAME]` - Build configuration option `EXAMPLES_NIMBLE_BLEESS_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NIMBLE_BLEESS_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NIMBLE_BLEESS_PROGNAME}`
- `[bleess.h:bleess_gap_init]` - Public function declaration `bleess_gap_init()`
- `[bleess.h:bleess_gap_on_reset]` - Public function declaration `bleess_gap_on_reset()`
- `[bleess.h:bleess_gap_on_sync]` - Public function declaration `bleess_gap_on_sync()`
- `[bleess.h:bleess_gatt_init]` - Public function declaration `bleess_gatt_init()`
- `[bleess.h:bleess_gatt_register_cb]` - Public function declaration `bleess_gatt_register_cb()`
- `[bleess.h:bleess_gatt_update]` - Public function declaration `bleess_gatt_update()`
- `[nimble_bleess_main.c:main]` - Application entry point `main()`
- `[bleess_gap.c:bleess_gap_init]` - Public function `bleess_gap_init()`
- `[bleess_gap.c:bleess_gap_on_reset]` - Public function `bleess_gap_on_reset()`
- `[bleess_gap.c:bleess_gap_on_sync]` - Public function `bleess_gap_on_sync()`
- `[bleess_gatt.c:bleess_gatt_register_cb]` - Public function `bleess_gatt_register_cb()`
- `[bleess_gatt.c:bleess_gatt_init]` - Public function `bleess_gatt_init()`
- `[bleess_gatt.c:bleess_gatt_update]` - Public function `bleess_gatt_update()`

## Invariants
- `[Kconfig:depends on NIMBLE && NIMBLE_ROLE_PERIPHERAL]` - Requires kernel/app configuration `NIMBLE && NIMBLE_ROLE_PERIPHERAL`
- `[nimble_bleess_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`
- `[nimble_bleess_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[nimble_bleess_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[bleess_gap.c:printf]` - Writes formatted output to standard output via `printf()`
- `[bleess_gatt.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
