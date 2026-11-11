# mount

## Overview
File system mount example (`mount`). Enable the file system mount example

## Interface
- `[Kconfig:EXAMPLES_MOUNT]` - Build configuration option `EXAMPLES_MOUNT`
- `[Kconfig:EXAMPLES_MOUNT_BLOCKDEVICE]` - Build configuration option `EXAMPLES_MOUNT_BLOCKDEVICE`
- `[Makefile:PROGNAME]` - Registers application/module target `mount`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `mount`
- `[mount.h:create_ramdisk]` - Public function declaration `create_ramdisk()`
- `[mount_main.c:main]` - Application entry point `main()`
- `[ramdisk.c:create_ramdisk]` - Public function `create_ramdisk()`

## Invariants
- `[mount.h:#error]` - Compile-time precondition: CONFIG_FS_FAT required in this configuration
- `[mount.h:CONFIG_EXAMPLES_MOUNT_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_MOUNT_DEVNAME`
- `[mount.h:CONFIG_FS_FAT]` - Configuration guard on `CONFIG_FS_FAT`
- `[mount.h:CONFIG_EXAMPLES_MOUNT_SECTORSIZE]` - Configuration guard on `CONFIG_EXAMPLES_MOUNT_SECTORSIZE`
- `[mount.h:CONFIG_EXAMPLES_MOUNT_NSECTORS]` - Configuration guard on `CONFIG_EXAMPLES_MOUNT_NSECTORS`
- `[mount_main.c:CONFIG_EXAMPLES_MOUNT_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_MOUNT_DEVNAME`
- `[ramdisk.c:CONFIG_EXAMPLES_MOUNT_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_MOUNT_DEVNAME`

## Side Effects
- `[mount.h:/dev/ram]` - Opens or interacts with VFS/device path `/dev/ram`
- `[mount_main.c:/mnt/fs]` - Opens or interacts with VFS/device path `/mnt/fs`
- `[mount_main.c:/mnt/fs/NewDir1]` - Opens or interacts with VFS/device path `/mnt/fs/NewDir1`
- `[mount_main.c:/mnt/fs/NewDir1/WrTest2.txt]` - Opens or interacts with VFS/device path `/mnt/fs/NewDir1/WrTest2.txt`
- `[mount_main.c:/mnt/fs/NewDir2]` - Opens or interacts with VFS/device path `/mnt/fs/NewDir2`
- `[mount_main.c:open]` - Opens device nodes or files via `open()`
- `[mount_main.c:mount]` - Mounts filesystems via `mount()`
- `[mount_main.c:umount]` - Unmounts filesystems via `umount()`
- `[mount_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[mount_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[mount_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[ramdisk.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[ramdisk.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
