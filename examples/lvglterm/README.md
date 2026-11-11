# lvglterm

## Overview
LVGL Terminal (`lvglterm`). Enable LVGL Terminal

## Interface
- `[Kconfig:EXAMPLES_LVGLTERM]` - Build configuration option `EXAMPLES_LVGLTERM`
- `[Kconfig:EXAMPLES_LVGLTERM_INPUT_TOUCH]` - Build configuration option `EXAMPLES_LVGLTERM_INPUT_TOUCH`
- `[Makefile:PROGNAME]` - Registers application/module target `lvglterm`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `lvglterm`
- `[lvglterm.h:lvglterm_send_input]` - Public function declaration `lvglterm_send_input()`
- `[lvglterm.h:lvglterm_add_output]` - Public function declaration `lvglterm_add_output()`
- `[lvglterm.h:lvglterm_input_create]` - Public function declaration `lvglterm_input_create()`
- `[lvglterm.h:lvglterm_input_poll]` - Public function declaration `lvglterm_input_poll()`
- `[lvglterm.c:lvglterm_send_input]` - Public function `lvglterm_send_input()`
- `[lvglterm.c:lvglterm_add_output]` - Public function `lvglterm_add_output()`
- `[lvglterm.c:main]` - Application entry point `main()`
- `[lvglterm_kbd.c:lvglterm_input_create]` - Public function `lvglterm_input_create()`
- `[lvglterm_kbd.c:lvglterm_input_poll]` - Public function `lvglterm_input_poll()`
- `[lvglterm_touch.c:lvglterm_input_create]` - Public function `lvglterm_input_create()`
- `[lvglterm_touch.c:lvglterm_input_poll]` - Public function `lvglterm_input_poll()`

## Invariants
- `[Kconfig:depends on GRAPHICS_LVGL]` - Requires kernel/app configuration `GRAPHICS_LVGL`
- `[Kconfig:depends on PSEUDOTERM]` - Requires kernel/app configuration `PSEUDOTERM`
- `[Kconfig:depends on INPUT_KEYBOARD]` - Requires kernel/app configuration `INPUT_KEYBOARD`
- `[lvglterm.c:#error]` - Compile-time precondition: posix_spawn() should be enabled in the configuration
- `[lvglterm.c:#error]` - Compile-time precondition: Pseudo-Terminal (PTY) support should be enabled in the configuration
- `[lvglterm.c:#error]` - Compile-time precondition: LVGL Font UNSCII 8 should be enabled in the configuration
- `[lvglterm.c:#error]` - Compile-time precondition: LVGL Font UNSCII 16 should be enabled in the configuration
- `[lvglterm.c:CONFIG_LIBC_EXECFUNCS]` - Configuration guard on `CONFIG_LIBC_EXECFUNCS`
- `[lvglterm.c:CONFIG_PSEUDOTERM]` - Configuration guard on `CONFIG_PSEUDOTERM`
- `[lvglterm.c:CONFIG_EXAMPLES_LVGLTERM_FONT_UNSCII_8]` - Configuration guard on `CONFIG_EXAMPLES_LVGLTERM_FONT_UNSCII_8`
- `[lvglterm.c:CONFIG_LV_FONT_UNSCII_8]` - Configuration guard on `CONFIG_LV_FONT_UNSCII_8`
- `[lvglterm.c:DEBUGASSERT]` - Runtime state and non-null pointer assertions via `DEBUGASSERT()`
- `[lvglterm_kbd.c:CONFIG_INPUT_KEYBOARD_BYTESTREAM]` - Configuration guard on `CONFIG_INPUT_KEYBOARD_BYTESTREAM`
- `[lvglterm_kbd.c:argc]` - Validates command-line argument count `argc`
- `[lvglterm_touch.c:DEBUGASSERT]` - Runtime state and non-null pointer assertions via `DEBUGASSERT()`

## Side Effects
- `[lvglterm.c:/dev/lcd0]` - Opens or interacts with VFS/device path `/dev/lcd0`
- `[lvglterm.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[lvglterm.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[lvglterm.c:posix_spawn]` - Spawns child processes via `posix_spawn()`
- `[lvglterm.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[lvglterm.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[lvglterm_kbd.c:open]` - Opens device nodes or files via `open()`
- `[lvglterm_kbd.c:read]` - Reads bytes from file or device descriptors via `read()`

## Verification
- Run: `make test`
