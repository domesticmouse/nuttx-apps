# lvgldemo

## Overview
LVGL Demo (`lvgldemo`). Enable build the Light and Versatile Graphics Library Demo programs

## Interface
- `[Kconfig:EXAMPLES_LVGLDEMO]` - Build configuration option `EXAMPLES_LVGLDEMO`
- `[Kconfig:EXAMPLES_LVGLDEMO_PRIORITY]` - Build configuration option `EXAMPLES_LVGLDEMO_PRIORITY`
- `[Makefile:PROGNAME]` - Registers application/module target `lvgldemo`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `lvgldemo`
- `[lvgldemo.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on GRAPHICS_LVGL]` - Requires kernel/app configuration `GRAPHICS_LVGL`
- `[Kconfig:depends on INPUT_TOUCHSCREEN]` - Requires kernel/app configuration `INPUT_TOUCHSCREEN`
- `[lvgldemo.c:CONFIG_LV_USE_NUTTX_LIBUV]` - Configuration guard on `CONFIG_LV_USE_NUTTX_LIBUV`
- `[lvgldemo.c:CONFIG_UINPUT_TOUCH]` - Configuration guard on `CONFIG_UINPUT_TOUCH`
- `[lvgldemo.c:CONFIG_LV_USE_NUTTX_LCD]` - Configuration guard on `CONFIG_LV_USE_NUTTX_LCD`
- `[lvgldemo.c:CONFIG_INPUT_TOUCHSCREEN]` - Configuration guard on `CONFIG_INPUT_TOUCHSCREEN`

## Side Effects
- `[lvgldemo.c:/dev/lcd0]` - Opens or interacts with VFS/device path `/dev/lcd0`

## Verification
- Run: `make test`
