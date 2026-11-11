# lvgltouch

## Overview
LVGL touchscreen diagnostic (`lvgltouch`). Show the touchscreen state and coordinates on the display.

## Interface
- `[Kconfig:EXAMPLES_LVGLTOUCH]` - Build configuration option `EXAMPLES_LVGLTOUCH`
- `[Kconfig:EXAMPLES_LVGLTOUCH_PROGNAME]` - Build configuration option `EXAMPLES_LVGLTOUCH_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LVGLTOUCH_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_LVGLTOUCH_PROGNAME}`
- `[lvgltouch_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on GRAPHICS_LVGL && INPUT_TOUCHSCREEN]` - Requires kernel/app configuration `GRAPHICS_LVGL && INPUT_TOUCHSCREEN`
- `[Kconfig:depends on !LV_USE_NUTTX_LCD]` - Requires kernel/app configuration `!LV_USE_NUTTX_LCD`
- `[lvgltouch_main.c:CONFIG_LV_USE_NUTTX_LCD]` - Configuration guard on `CONFIG_LV_USE_NUTTX_LCD`

## Side Effects
- `[lvgltouch_main.c:/dev/lcd0]` - Opens or interacts with VFS/device path `/dev/lcd0`

## Verification
- Run: `make test`
