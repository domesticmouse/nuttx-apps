# charger

## Overview
Battery charger example (`charger`). This application is an example of using charger device.

## Interface
- `[Kconfig:EXAMPLES_CHARGER]` - Build configuration option `EXAMPLES_CHARGER`
- `[Kconfig:EXAMPLES_CHARGER_DEVNAME]` - Build configuration option `EXAMPLES_CHARGER_DEVNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_CHARGER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_CHARGER_PROGNAME}`
- `[charger_main.c:main]` - Application entry point `main()`
- `[charger_main.c:getopt]` - Command-line option parser supporting flags `"v"`

## Invariants
- `[charger_main.c:CONFIG_EXAMPLES_CHARGER_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_CHARGER_DEVNAME`

## Side Effects
- `[charger_main.c:/dev/bat]` - Opens or interacts with VFS/device path `/dev/bat`
- `[charger_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[charger_main.c:open]` - Opens device nodes or files via `open()`
- `[charger_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
