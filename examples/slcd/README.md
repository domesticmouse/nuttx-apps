# slcd

## Overview
Segment LCD test (`slcd`). Enables a simple test of an alphanumer, segment LCD

## Interface
- `[Kconfig:EXAMPLES_SLCD]` - Build configuration option `EXAMPLES_SLCD`
- `[Kconfig:EXAMPLES_SLCD_DEVNAME]` - Build configuration option `EXAMPLES_SLCD_DEVNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `slcd`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `slcd`
- `[slcd_main.c:struct slcd_test_s]` - Structure definition `slcd_test_s`
- `[slcd_main.c:slcd_dumpbuffer]` - Public function `slcd_dumpbuffer()`
- `[slcd_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SLCD]` - Requires kernel/app configuration `SLCD`
- `[slcd_main.c:CONFIG_EXAMPLES_SLCD_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_SLCD_DEVNAME`
- `[slcd_main.c:CONFIG_STDIO_LINEBUFFER]` - Configuration guard on `CONFIG_STDIO_LINEBUFFER`
- `[slcd_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[slcd_main.c:/dev/slcd0]` - Opens or interacts with VFS/device path `/dev/slcd0`
- `[slcd_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[slcd_main.c:open]` - Opens device nodes or files via `open()`
- `[slcd_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[slcd_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
