# mtdpart

## Overview
MTD partition test (`mtdpart`). Enable the MTD partition test example.

## Interface
- `[Kconfig:EXAMPLES_MTDPART]` - Build configuration option `EXAMPLES_MTDPART`
- `[Kconfig:EXAMPLES_MTDPART_ARCHINIT]` - Build configuration option `EXAMPLES_MTDPART_ARCHINIT`
- `[Makefile:PROGNAME]` - Registers application/module target `mtdpart`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `mtdpart`
- `[mtdpart_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on MTD_PARTITION && BUILD_FLAT]` - Requires kernel/app configuration `MTD_PARTITION && BUILD_FLAT`
- `[Kconfig:depends on !EXAMPLES_MTDPART_ARCHINIT]` - Requires kernel/app configuration `!EXAMPLES_MTDPART_ARCHINIT`
- `[mtdpart_main.c:#error]` - Compile-time precondition: CONFIG_MTD_PARTITION is required
- `[mtdpart_main.c:#error]` - Compile-time precondition: CONFIG_RAMMTD is required without CONFIG_EXAMPLES_MTDPART_ARCHINIT
- `[mtdpart_main.c:#error]` - Compile-time precondition: CONFIG_EXAMPLES_MTDPART_NPARTITIONS must be greater than 0
- `[mtdpart_main.c:CONFIG_MTD_PARTITION]` - Configuration guard on `CONFIG_MTD_PARTITION`
- `[mtdpart_main.c:CONFIG_EXAMPLES_MTDPART_ARCHINIT]` - Configuration guard on `CONFIG_EXAMPLES_MTDPART_ARCHINIT`
- `[mtdpart_main.c:CONFIG_RAMMTD]` - Configuration guard on `CONFIG_RAMMTD`
- `[mtdpart_main.c:CONFIG_RAMMTD_ERASESIZE]` - Configuration guard on `CONFIG_RAMMTD_ERASESIZE`

## Side Effects
- `[mtdpart_main.c:/dev/mtd%d]` - Opens or interacts with VFS/device path `/dev/mtd%d`
- `[mtdpart_main.c:/dev/mtd0]` - Opens or interacts with VFS/device path `/dev/mtd0`
- `[mtdpart_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[mtdpart_main.c:open]` - Opens device nodes or files via `open()`
- `[mtdpart_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[mtdpart_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[mtdpart_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
