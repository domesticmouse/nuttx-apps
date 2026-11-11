# userfs

## Overview
UserFS test (`userfs`). Enables a simple test of the UserFS

## Interface
- `[Kconfig:EXAMPLES_USERFS]` - Build configuration option `EXAMPLES_USERFS`
- `[Kconfig:EXAMPLES_USERFS_PROGNAME]` - Build configuration option `EXAMPLES_USERFS_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_USERFS_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_USERFS_PROGNAME}`
- `[userfs_main.c:struct ufstest_file_s]` - Structure definition `ufstest_file_s`
- `[userfs_main.c:struct ufstest_openfile_s]` - Structure definition `ufstest_openfile_s`
- `[userfs_main.c:struct ufstest_opendir_s]` - Structure definition `ufstest_opendir_s`
- `[userfs_main.c:ufstest_daemon]` - Public function `ufstest_daemon()`
- `[userfs_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on FS_USERFS]` - Requires kernel/app configuration `FS_USERFS`

## Side Effects
- `[userfs_main.c:/mnt/ufstest]` - Opens or interacts with VFS/device path `/mnt/ufstest`
- `[userfs_main.c:task_create]` - Spawns NuttX tasks via `task_create()`

## Verification
- Run: `make test`
