# romfs

## Overview
ROMFS example (`romfs`). Enable the ROMFS example

## Interface
- `[Kconfig:EXAMPLES_ROMFS]` - Build configuration option `EXAMPLES_ROMFS`
- `[Kconfig:EXAMPLES_ROMFS_RAMDEVNO]` - Build configuration option `EXAMPLES_ROMFS_RAMDEVNO`
- `[Makefile:PROGNAME]` - Registers application/module target `romfs`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `romfs`
- `[romfs_main.c:struct node_s]` - Structure definition `node_s`
- `[romfs_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on FS_ROMFS && BUILD_FLAT && BOARDCTL_ROMDISK]` - Requires kernel/app configuration `FS_ROMFS && BUILD_FLAT && BOARDCTL_ROMDISK`
- `[romfs_main.c:#error]` - Compile-time precondition: Mountpoint support is disabled
- `[romfs_main.c:#error]` - Compile-time precondition: ROMFS support not enabled
- `[romfs_main.c:CONFIG_EXAMPLES_ROMFS_RAMDEVNO]` - Configuration guard on `CONFIG_EXAMPLES_ROMFS_RAMDEVNO`
- `[romfs_main.c:CONFIG_EXAMPLES_ROMFS_SECTORSIZE]` - Configuration guard on `CONFIG_EXAMPLES_ROMFS_SECTORSIZE`
- `[romfs_main.c:CONFIG_EXAMPLES_ROMFS_MOUNTPOINT]` - Configuration guard on `CONFIG_EXAMPLES_ROMFS_MOUNTPOINT`
- `[romfs_main.c:CONFIG_DISABLE_MOUNTPOINT]` - Configuration guard on `CONFIG_DISABLE_MOUNTPOINT`

## Side Effects
- `[romfs_main.c:/dev/ram]` - Opens or interacts with VFS/device path `/dev/ram`
- `[romfs_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[romfs_main.c:open]` - Opens device nodes or files via `open()`
- `[romfs_main.c:mmap]` - Maps device or shared memory buffers via `mmap()`
- `[romfs_main.c:mount]` - Mounts filesystems via `mount()`
- `[romfs_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[romfs_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
