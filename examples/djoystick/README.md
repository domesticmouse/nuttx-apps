# djoystick

## Overview
Discrete joystick example (`djoystick`). Enable the discrete joystick example

## Interface
- `[Kconfig:EXAMPLES_DJOYSTICK]` - Build configuration option `EXAMPLES_DJOYSTICK`
- `[Kconfig:EXAMPLES_DJOYSTICK_DEVNAME]` - Build configuration option `EXAMPLES_DJOYSTICK_DEVNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `djoy`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `djoy`
- `[djoy_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on INPUT_DJOYSTICK && ENABLE_ALL_SIGNALS]` - Requires kernel/app configuration `INPUT_DJOYSTICK && ENABLE_ALL_SIGNALS`
- `[djoy_main.c:#error]` - Compile-time precondition: CONFIG_INPUT_DJOYSTICK is not defined in the configuration
- `[djoy_main.c:CONFIG_INPUT_DJOYSTICK]` - Configuration guard on `CONFIG_INPUT_DJOYSTICK`
- `[djoy_main.c:CONFIG_EXAMPLES_DJOYSTICK_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_DJOYSTICK_DEVNAME`
- `[djoy_main.c:CONFIG_EXAMPLES_DJOYSTICK_SIGNO]` - Configuration guard on `CONFIG_EXAMPLES_DJOYSTICK_SIGNO`

## Side Effects
- `[djoy_main.c:/dev/djoy0]` - Opens or interacts with VFS/device path `/dev/djoy0`
- `[djoy_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[djoy_main.c:open]` - Opens device nodes or files via `open()`
- `[djoy_main.c:sigwaitinfo]` - Waits synchronously for signals via `sigwaitinfo()`
- `[djoy_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[djoy_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
