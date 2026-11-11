# pppd

## Overview
pppd client example (`pppd`). Enable the pppd client example

## Interface
- `[Kconfig:EXAMPLES_PPPD]` - Build configuration option `EXAMPLES_PPPD`
- `[Kconfig:EXAMPLES_PPPD_STACKSIZE]` - Build configuration option `EXAMPLES_PPPD_STACKSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `pppd`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `pppd`
- `[pppd_main.c:main]` - Application entry point `main()`

## Invariants
- `[pppd_main.c:CONFIG_NETUTILS_PPPD_PAP]` - Configuration guard on `CONFIG_NETUTILS_PPPD_PAP`

## Side Effects
- `[pppd_main.c:/dev/ttyS1]` - Opens or interacts with VFS/device path `/dev/ttyS1`

## Verification
- Run: `make test`
