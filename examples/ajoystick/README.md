# ajoystick

## Overview
Analog joystick example (`ajoystick`). Enable the analog joystick example

## Interface
- `[Kconfig:EXAMPLES_AJOYSTICK]` - Build configuration option `EXAMPLES_AJOYSTICK`
- `[Kconfig:EXAMPLES_AJOYSTICK_DEVNAME]` - Build configuration option `EXAMPLES_AJOYSTICK_DEVNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `ajoy`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `ajoy`
- `[ajoy_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on INPUT_AJOYSTICK]` - Requires kernel/app configuration `INPUT_AJOYSTICK`
- `[ajoy_main.c:#error]` - Compile-time precondition: CONFIG_AJOYSTICK is not defined in the configuration
- `[ajoy_main.c:CONFIG_AJOYSTICK]` - Configuration guard on `CONFIG_AJOYSTICK`
- `[ajoy_main.c:CONFIG_EXAMPLES_AJOYSTICK_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_AJOYSTICK_DEVNAME`
- `[ajoy_main.c:CONFIG_EXAMPLES_AJOYSTICK_SIGNO]` - Configuration guard on `CONFIG_EXAMPLES_AJOYSTICK_SIGNO`

## Side Effects
- `[ajoy_main.c:/dev/ajoy0]` - Opens or interacts with VFS/device path `/dev/ajoy0`
- `[ajoy_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[ajoy_main.c:open]` - Opens device nodes or files via `open()`
- `[ajoy_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[ajoy_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
