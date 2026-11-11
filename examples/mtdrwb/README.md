# mtdrwb

## Overview
MTD R/W buffer test (`mtdrwb`). Enable the MTD R/W buffer test example.

## Interface
- `[Kconfig:EXAMPLES_MTDRWB]` - Build configuration option `EXAMPLES_MTDRWB`
- `[Kconfig:EXAMPLES_MTDRWB_PROGNAME]` - Build configuration option `EXAMPLES_MTDRWB_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MTDRWB_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MTDRWB_PROGNAME}`
- `[mtdrwb_main.c:struct mtdweb_filedesc_s]` - Structure definition `mtdweb_filedesc_s`
- `[mtdrwb_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on (MTD_WRBUFFER || MTD_READAHEAD) && BUILD_FLAT]` - Requires kernel/app configuration `(MTD_WRBUFFER || MTD_READAHEAD) && BUILD_FLAT`
- `[Kconfig:depends on !EXAMPLES_MTDRWB_ARCHINIT]` - Requires kernel/app configuration `!EXAMPLES_MTDRWB_ARCHINIT`
- `[Kconfig:depends on !EXAMPLES_MTDRWB_ARCHINIT]` - Requires kernel/app configuration `!EXAMPLES_MTDRWB_ARCHINIT`
- `[mtdrwb_main.c:#error]` - Compile-time precondition: CONFIG_MTD_WRBUFFER or CONFIG_MTD_READAHEAD must be selected
- `[mtdrwb_main.c:#error]` - Compile-time precondition: CONFIG_RAMMTD is required without CONFIG_EXAMPLES_MTDRWB_ARCHINIT
- `[mtdrwb_main.c:CONFIG_EXAMPLES_MTDRWB]` - Configuration guard on `CONFIG_EXAMPLES_MTDRWB`
- `[mtdrwb_main.c:CONFIG_MTD_WRBUFFER]` - Configuration guard on `CONFIG_MTD_WRBUFFER`
- `[mtdrwb_main.c:CONFIG_EXAMPLES_MTDRWB_ARCHINIT]` - Configuration guard on `CONFIG_EXAMPLES_MTDRWB_ARCHINIT`
- `[mtdrwb_main.c:CONFIG_RAMMTD]` - Configuration guard on `CONFIG_RAMMTD`

## Side Effects
- `[mtdrwb_main.c:/dev/mtd0]` - Opens or interacts with VFS/device path `/dev/mtd0`
- `[mtdrwb_main.c:/dev/mtdblock0]` - Opens or interacts with VFS/device path `/dev/mtdblock0`
- `[mtdrwb_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[mtdrwb_main.c:open]` - Opens device nodes or files via `open()`
- `[mtdrwb_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[mtdrwb_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[mtdrwb_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
