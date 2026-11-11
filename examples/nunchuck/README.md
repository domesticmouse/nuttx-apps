# nunchuck

## Overview
Nunchuck joystick example (`nunchuck`). Enable the nunchuck joystick example

## Interface
- `[Kconfig:EXAMPLES_NUNCHUCK]` - Build configuration option `EXAMPLES_NUNCHUCK`
- `[Kconfig:EXAMPLES_NUNCHUCK_DEVNAME]` - Build configuration option `EXAMPLES_NUNCHUCK_DEVNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `nunchuck`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `nunchuck`
- `[nunchuck_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on INPUT_NUNCHUCK]` - Requires kernel/app configuration `INPUT_NUNCHUCK`
- `[nunchuck_main.c:#error]` - Compile-time precondition: CONFIG_NUNCHUCK is not defined in the configuration
- `[nunchuck_main.c:CONFIG_INPUT_NUNCHUCK]` - Configuration guard on `CONFIG_INPUT_NUNCHUCK`
- `[nunchuck_main.c:CONFIG_EXAMPLES_NUNCHUCK_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_NUNCHUCK_DEVNAME`
- `[nunchuck_main.c:CONFIG_DEBUG_INPUT]` - Configuration guard on `CONFIG_DEBUG_INPUT`

## Side Effects
- `[nunchuck_main.c:/dev/nunchuck0]` - Opens or interacts with VFS/device path `/dev/nunchuck0`
- `[nunchuck_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[nunchuck_main.c:open]` - Opens device nodes or files via `open()`
- `[nunchuck_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[nunchuck_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
