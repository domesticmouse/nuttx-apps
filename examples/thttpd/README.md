# thttpd

## Overview
THTTPD web server example (`thttpd`). Enable the THTTPD web server example

## Interface
- `[Kconfig:EXAMPLES_THTTPD]` - Build configuration option `EXAMPLES_THTTPD`
- `[Kconfig:EXAMPLES_THTTPD_NOMAC]` - Build configuration option `EXAMPLES_THTTPD_NOMAC`
- `[Makefile:PROGNAME]` - Registers application/module target `thttp`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `thttpd`
- `[thttpd_main.c:main]` - Application entry point `main()`
- **content**: [`./content/README.md`](./content/README.md) - Intermediate grouping directory for `thttpd/content`, organizing submodules: hello, tasks.

## Invariants
- `[Kconfig:depends on FS_ROMFS && BUILD_FLAT]` - Requires kernel/app configuration `FS_ROMFS && BUILD_FLAT`
- `[thttpd_main.c:#error]` - Compile-time precondition: You must not disable loadable modules via CONFIG_BINFMT_DISABLE in your configuration file
- `[thttpd_main.c:#error]` - Compile-time precondition: You must select CONFIG_NXFLAT in your configuration file
- `[thttpd_main.c:#error]` - Compile-time precondition: You must select CONFIG_FS_ROMFS in your configuration file
- `[thttpd_main.c:#error]` - Compile-time precondition: You must not disable mountpoints via CONFIG_DISABLE_MOUNTPOINT in your configuration file
- `[thttpd_main.c:#error]` - Compile-time precondition: CONFIG_BOARDCTL_ROMDISK should be enabled in the configuration file
- `[thttpd_main.c:#error]` - Compile-time precondition: You must select CONFIG_BUILTIN=y in your configuration file
- `[thttpd_main.c:#error]` - Compile-time precondition: You must select CONFIG_FS_BINFS=y in your configuration file
- `[thttpd_main.c:#error]` - Compile-time precondition: CONFIG_FS_UNIONFS=y is required in this configuration
- `[thttpd_main.c:CONFIG_THTTPD_NXFLAT]` - Configuration guard on `CONFIG_THTTPD_NXFLAT`
- `[thttpd_main.c:CONFIG_NET_SLIP]` - Configuration guard on `CONFIG_NET_SLIP`
- `[thttpd_main.c:CONFIG_BINFMT_DISABLE]` - Configuration guard on `CONFIG_BINFMT_DISABLE`
- `[thttpd_main.c:CONFIG_NXFLAT]` - Configuration guard on `CONFIG_NXFLAT`

## Side Effects
- `[thttpd_main.c:/dev/ram0]` - Opens or interacts with VFS/device path `/dev/ram0`
- `[thttpd_main.c:/dev/ttyS1]` - Opens or interacts with VFS/device path `/dev/ttyS1`
- `[thttpd_main.c:/mnt/tmp1]` - Opens or interacts with VFS/device path `/mnt/tmp1`
- `[thttpd_main.c:/mnt/tmp2]` - Opens or interacts with VFS/device path `/mnt/tmp2`
- `[thttpd_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[thttpd_main.c:mount]` - Mounts filesystems via `mount()`
- `[thttpd_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
