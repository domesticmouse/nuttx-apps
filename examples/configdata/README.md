# configdata

## Overview
Config Data example / unit test (`configdata`). Enable the Config Data example

## Interface
- `[Kconfig:EXAMPLES_CONFIGDATA]` - Build configuration option `EXAMPLES_CONFIGDATA`
- `[Kconfig:EXAMPLES_CONFIGDATA_ARCHINIT]` - Build configuration option `EXAMPLES_CONFIGDATA_ARCHINIT`
- `[Makefile:PROGNAME]` - Registers application/module target `configdata`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `configdata`
- `[configdata_main.c:struct configdata_entrydesc_s]` - Structure definition `configdata_entrydesc_s`
- `[configdata_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on !EXAMPLES_CONFIGDATA_ARCHINIT]` - Requires kernel/app configuration `!EXAMPLES_CONFIGDATA_ARCHINIT`
- `[configdata_main.c:CONFIG_EXAMPLES_CONFIGDATA_ARCHINIT]` - Configuration guard on `CONFIG_EXAMPLES_CONFIGDATA_ARCHINIT`
- `[configdata_main.c:CONFIG_RAMMTD_ERASESIZE]` - Configuration guard on `CONFIG_RAMMTD_ERASESIZE`
- `[configdata_main.c:CONFIG_EXAMPLES_CONFIGDATA_NEBLOCKS]` - Configuration guard on `CONFIG_EXAMPLES_CONFIGDATA_NEBLOCKS`
- `[configdata_main.c:CONFIG_EXAMPLES_CONFIGDATA_MAXSIZE]` - Configuration guard on `CONFIG_EXAMPLES_CONFIGDATA_MAXSIZE`

## Side Effects
- `[configdata_main.c:/dev/config]` - Opens or interacts with VFS/device path `/dev/config`
- `[configdata_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[configdata_main.c:open]` - Opens device nodes or files via `open()`
- `[configdata_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
