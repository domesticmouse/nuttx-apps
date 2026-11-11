# nimble_bleprph

## Overview
NimBLE peripheral (`nimble_bleprph`). Enable the nimble peripheral example

## Interface
- `[Kconfig:EXAMPLES_NIMBLE_BLEPRPH]` - Build configuration option `EXAMPLES_NIMBLE_BLEPRPH`
- `[Kconfig:EXAMPLES_NIMBLE_BLEPRPH_PROGNAME]` - Build configuration option `EXAMPLES_NIMBLE_BLEPRPH_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NIMBLE_BLEPRPH_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NIMBLE_BLEPRPH_PROGNAME}`
- `[bleprph.h:gatt_svr_register_cb]` - Public function declaration `gatt_svr_register_cb()`
- `[bleprph.h:gatt_svr_init]` - Public function declaration `gatt_svr_init()`
- `[bleprph.h:print_addr]` - Public function declaration `print_addr()`
- `[nimble_bleprph_main.c:main]` - Application entry point `main()`
- `[gatt_svr.c:gatt_svr_register_cb]` - Public function `gatt_svr_register_cb()`
- `[gatt_svr.c:gatt_svr_init]` - Public function `gatt_svr_init()`
- `[misc.c:print_addr]` - Public function `print_addr()`

## Invariants
- `[nimble_bleprph_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`
- `[nimble_bleprph_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[nimble_bleprph_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[gatt_svr.c:printf]` - Writes formatted output to standard output via `printf()`
- `[misc.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
