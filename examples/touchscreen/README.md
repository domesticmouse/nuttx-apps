# touchscreen

## Overview
Touchscreen example (`touchscreen`). Enable the touchscreen example

## Interface
- `[Kconfig:EXAMPLES_TOUCHSCREEN]` - Build configuration option `EXAMPLES_TOUCHSCREEN`
- `[Kconfig:EXAMPLES_TOUCHSCREEN_MINOR]` - Build configuration option `EXAMPLES_TOUCHSCREEN_MINOR`
- `[Makefile:PROGNAME]` - Registers application/module target `tc`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `tc`
- `[tc_main.c:main]` - Application entry point `main()`

## Invariants
- `[tc.h:#error]` - Compile-time precondition: Input device support is not enabled (CONFIG_INPUT)
- `[tc.h:CONFIG_INPUT]` - Configuration guard on `CONFIG_INPUT`
- `[tc.h:CONFIG_EXAMPLES_TOUCHSCREEN_MINOR]` - Configuration guard on `CONFIG_EXAMPLES_TOUCHSCREEN_MINOR`
- `[tc.h:CONFIG_EXAMPLES_TOUCHSCREEN_MOUSE]` - Configuration guard on `CONFIG_EXAMPLES_TOUCHSCREEN_MOUSE`
- `[tc.h:CONFIG_EXAMPLES_TOUCHSCREEN_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_TOUCHSCREEN_DEVPATH`
- `[tc_main.c:CONFIG_EXAMPLES_TOUCHSCREEN_MOUSE]` - Configuration guard on `CONFIG_EXAMPLES_TOUCHSCREEN_MOUSE`
- `[tc_main.c:CONFIG_INPUT_MOUSE_WHEEL]` - Configuration guard on `CONFIG_INPUT_MOUSE_WHEEL`
- `[tc_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[tc.h:/dev/input0]` - Opens or interacts with VFS/device path `/dev/input0`
- `[tc.h:/dev/mouse0]` - Opens or interacts with VFS/device path `/dev/mouse0`
- `[tc_main.c:open]` - Opens device nodes or files via `open()`
- `[tc_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[tc_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
