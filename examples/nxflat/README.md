# nxflat

## Overview
NXFLAT example (`nxflat`). Enable the NXFLAT example

## Interface
- `[Kconfig:EXAMPLES_NXFLAT]` - Build configuration option `EXAMPLES_NXFLAT`
- `[Makefile:PROGNAME]` - Registers application/module target `nxflat`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `nxflat`
- `[nxflat_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NXFLAT]` - Requires kernel/app configuration `NXFLAT`
- `[nxflat_main.c:#error]` - Compile-time precondition: You must select CONFIG_NXFLAT in your configuration file
- `[nxflat_main.c:#error]` - Compile-time precondition: You must select CONFIG_FS_ROMFS in your configuration file
- `[nxflat_main.c:#error]` - Compile-time precondition: You must not disable mountpoints via CONFIG_DISABLE_MOUNTPOINT in your configuration file
- `[nxflat_main.c:#error]` - Compile-time precondition: You must not disable loadable modules via CONFIG_BINFMT_DISABLE in your configuration file
- `[nxflat_main.c:#error]` - Compile-time precondition: CONFIG_BOARDCTL_ROMDISK should be enabled in the configuration file
- `[nxflat_main.c:CONFIG_NXFLAT]` - Configuration guard on `CONFIG_NXFLAT`
- `[nxflat_main.c:CONFIG_FS_ROMFS]` - Configuration guard on `CONFIG_FS_ROMFS`
- `[nxflat_main.c:CONFIG_DISABLE_MOUNTPOINT]` - Configuration guard on `CONFIG_DISABLE_MOUNTPOINT`
- `[nxflat_main.c:CONFIG_BINFMT_DISABLE]` - Configuration guard on `CONFIG_BINFMT_DISABLE`

## Side Effects
- `[nxflat_main.c:/dev/ram0]` - Opens or interacts with VFS/device path `/dev/ram0`
- `[nxflat_main.c:/mnt/romfs]` - Opens or interacts with VFS/device path `/mnt/romfs`
- `[nxflat_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nxflat_main.c:mount]` - Mounts filesystems via `mount()`
- `[nxflat_main.c:exec]` - Executes binary programs in-place via `exec()`

## Verification
- Run: `make test`
