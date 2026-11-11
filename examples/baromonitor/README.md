# baromonitor

## Overview
Barometer monitoring dashboard example (`baromonitor`). Enable the barometer monitoring dashboard.

## Interface
- `[Kconfig:EXAMPLES_BAROMONITOR]` - Build configuration option `EXAMPLES_BAROMONITOR`
- `[Kconfig:EXAMPLES_BAROMONITOR_PROGNAME]` - Build configuration option `EXAMPLES_BAROMONITOR_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_BAROMONITOR_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_BAROMONITOR_PROGNAME}`
- `[baromonitor_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on UORB]` - Requires kernel/app configuration `UORB`
- `[Kconfig:depends on LIBC_FLOATINGPOINT]` - Requires kernel/app configuration `LIBC_FLOATINGPOINT`
- `[Kconfig:depends on GRAPHICS_LVGL]` - Requires kernel/app configuration `GRAPHICS_LVGL`
- `[baromonitor_main.c:CONFIG_LV_USE_NUTTX_LIBUV]` - Configuration guard on `CONFIG_LV_USE_NUTTX_LIBUV`
- `[baromonitor_main.c:CONFIG_UINPUT_TOUCH]` - Configuration guard on `CONFIG_UINPUT_TOUCH`
- `[baromonitor_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[baromonitor_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[baromonitor_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
