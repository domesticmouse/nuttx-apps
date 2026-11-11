# keyboard

## Overview
Keyboard example (`keyboard`). Enable the keyboard example

## Interface
- `[Kconfig:EXAMPLES_KEYBOARD]` - Build configuration option `EXAMPLES_KEYBOARD`
- `[Kconfig:EXAMPLES_KEYBOARD_DEVPATH]` - Build configuration option `EXAMPLES_KEYBOARD_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `kbd`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `kbd`
- `[kbd_main.c:main]` - Application entry point `main()`

## Invariants
- `[kbd_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[kbd_main.c:open]` - Opens device nodes or files via `open()`
- `[kbd_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[kbd_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
