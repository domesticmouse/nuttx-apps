# sx127x_demo

## Overview
SX127x example (`sx127x_demo`).

## Interface
- `[Kconfig:EXAMPLES_SX127X]` - Build configuration option `EXAMPLES_SX127X`
- `[Kconfig:EXAMPLES_SX127X_RFFREQ]` - Build configuration option `EXAMPLES_SX127X_RFFREQ`
- `[Makefile:PROGNAME]` - Registers application/module target `sx127x`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `sx127x`
- `[sx127x_demo.c:struct args_s]` - Structure definition `args_s`
- `[sx127x_demo.c:enum app_mode_e]` - Enumeration `app_mode_e`
- `[sx127x_demo.c:enum app_modulation_e]` - Enumeration `app_modulation_e`
- `[sx127x_demo.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on LPWAN_SX127X]` - Requires kernel/app configuration `LPWAN_SX127X`
- `[sx127x_demo.c:CONFIG_LPWAN_SX127X_RXSUPPORT]` - Configuration guard on `CONFIG_LPWAN_SX127X_RXSUPPORT`
- `[sx127x_demo.c:CONFIG_LPWAN_SX127X_TXSUPPORT]` - Configuration guard on `CONFIG_LPWAN_SX127X_TXSUPPORT`

## Side Effects
- `[sx127x_demo.c:/dev/sx127x]` - Opens or interacts with VFS/device path `/dev/sx127x`
- `[sx127x_demo.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[sx127x_demo.c:open]` - Opens device nodes or files via `open()`
- `[sx127x_demo.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[sx127x_demo.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[sx127x_demo.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
