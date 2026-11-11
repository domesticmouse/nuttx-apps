# unionfs

## Overview
Union file system example (`unionfs`). Enable the Union File System example

## Interface
- `[Kconfig:EXAMPLES_UNIONFS]` - Build configuration option `EXAMPLES_UNIONFS`
- `[Kconfig:EXAMPLES_UNIONFS_MOUNTPT]` - Build configuration option `EXAMPLES_UNIONFS_MOUNTPT`
- `[Makefile:PROGNAME]` - Registers application/module target `unionfs`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `unionfs`
- `[unionfs_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on FS_ROMFS && FS_UNIONFS && BUILD_FLAT]` - Requires kernel/app configuration `FS_ROMFS && FS_UNIONFS && BUILD_FLAT`
- `[unionfs_main.c:#error]` - Compile-time precondition: Mountpoint support is disabled
- `[unionfs_main.c:#error]` - Compile-time precondition: ROMFS support not enabled
- `[unionfs_main.c:#error]` - Compile-time precondition: Union File System support not enabled
- `[unionfs_main.c:CONFIG_DISABLE_MOUNTPOINT]` - Configuration guard on `CONFIG_DISABLE_MOUNTPOINT`
- `[unionfs_main.c:CONFIG_FS_ROMFS]` - Configuration guard on `CONFIG_FS_ROMFS`
- `[unionfs_main.c:CONFIG_FS_UNIONFS]` - Configuration guard on `CONFIG_FS_UNIONFS`
- `[unionfs_main.c:CONFIG_EXAMPLES_UNIONFS_RAMDEVNO_A]` - Configuration guard on `CONFIG_EXAMPLES_UNIONFS_RAMDEVNO_A`

## Side Effects
- `[unionfs_main.c:/dev/ram]` - Opens or interacts with VFS/device path `/dev/ram`
- `[unionfs_main.c:/mnt/a]` - Opens or interacts with VFS/device path `/mnt/a`
- `[unionfs_main.c:/mnt/b]` - Opens or interacts with VFS/device path `/mnt/b`
- `[unionfs_main.c:/mnt/unionfs]` - Opens or interacts with VFS/device path `/mnt/unionfs`
- `[unionfs_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[unionfs_main.c:mount]` - Mounts filesystems via `mount()`
- `[unionfs_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
