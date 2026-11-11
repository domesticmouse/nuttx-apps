# hdc1008_demo

## Overview
HDC1008 driver example (`hdc1008_demo`). Enable the example application

## Interface
- `[Kconfig:EXAMPLES_HDC1008]` - Build configuration option `EXAMPLES_HDC1008`
- `[Makefile:PROGNAME]` - Registers application/module target `hdc1008`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `hdc1008`
- `[hdc1008_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_HDC1008]` - Requires kernel/app configuration `SENSORS_HDC1008`

## Side Effects
- `[hdc1008_main.c:/dev/hdc1008]` - Opens or interacts with VFS/device path `/dev/hdc1008`
- `[hdc1008_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[hdc1008_main.c:open]` - Opens device nodes or files via `open()`
- `[hdc1008_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[hdc1008_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
