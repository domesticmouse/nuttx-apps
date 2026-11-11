# bastest

## Overview
Setup Test Files for BAS (`bastest`). Mount the ROMFS file system containing the BAS test files at /mnt/romfs.  This selection depends both on INTERPRETER_BAS to provide the BASIC interpreter and and upon FS_ROMFS to provide support for the ROMFS file system.

## Interface
- `[Kconfig:EXAMPLES_BASTEST]` - Build configuration option `EXAMPLES_BASTEST`
- `[Kconfig:EXAMPLES_BASTEST_DEVMINOR]` - Build configuration option `EXAMPLES_BASTEST_DEVMINOR`
- `[Makefile:PROGNAME]` - Registers application/module target `bastest`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `bastest`
- `[bastest_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on FS_ROMFS && INTERPRETERS_BAS]` - Requires kernel/app configuration `FS_ROMFS && INTERPRETERS_BAS`
- `[bastest_main.c:#error]` - Compile-time precondition: You must select CONFIG_FS_ROMFS in your configuration file
- `[bastest_main.c:#error]` - Compile-time precondition: You must not disable mountpoints via CONFIG_DISABLE_MOUNTPOINT in your configuration file
- `[bastest_main.c:CONFIG_FS_ROMFS]` - Configuration guard on `CONFIG_FS_ROMFS`
- `[bastest_main.c:CONFIG_DISABLE_MOUNTPOINT]` - Configuration guard on `CONFIG_DISABLE_MOUNTPOINT`
- `[bastest_main.c:CONFIG_EXAMPLES_BASTEST_DEVMINOR]` - Configuration guard on `CONFIG_EXAMPLES_BASTEST_DEVMINOR`
- `[bastest_main.c:CONFIG_EXAMPLES_BASTEST_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_BASTEST_DEVPATH`

## Side Effects
- `[bastest_main.c:/dev/ram0]` - Opens or interacts with VFS/device path `/dev/ram0`
- `[bastest_main.c:/mnt/romfs]` - Opens or interacts with VFS/device path `/mnt/romfs`
- `[bastest_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[bastest_main.c:mount]` - Mounts filesystems via `mount()`
- `[bastest_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
