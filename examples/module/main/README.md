# main

## Overview
Module Example (`module/main`). Enable the module example

## Interface
- `[Kconfig:EXAMPLES_MODULE]` - Build configuration option `EXAMPLES_MODULE`
- `[Kconfig:EXAMPLES_MODULE_BUILTINFS]` - Build configuration option `EXAMPLES_MODULE_BUILTINFS`
- `[Makefile:PROGNAME]` - Registers application/module target `module`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `module`
- `[module_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on MODULE && BOARDCTL]` - Requires kernel/app configuration `MODULE && BOARDCTL`
- `[Kconfig:depends on (FS_ROMFS || FS_CROMFS) && BUILD_FLAT]` - Requires kernel/app configuration `(FS_ROMFS || FS_CROMFS) && BUILD_FLAT`
- `[Kconfig:depends on EXAMPLES_MODULE_BUILTINFS]` - Requires kernel/app configuration `EXAMPLES_MODULE_BUILTINFS`
- `[module_main.c:#error]` - Compile-time precondition: You must select CONFIG_MODULE in your configuration file
- `[module_main.c:#error]` - Compile-time precondition: You must select CONFIG_FS_ROMFS or CONFIG_FS_CROMFS in your configuration file
- `[module_main.c:#error]` - Compile-time precondition: You must not disable mountpoints via CONFIG_DISABLE_MOUNTPOINT in your configuration file
- `[module_main.c:CONFIG_EXAMPLES_MODULE_ROMFS]` - Configuration guard on `CONFIG_EXAMPLES_MODULE_ROMFS`
- `[module_main.c:CONFIG_MODULE]` - Configuration guard on `CONFIG_MODULE`
- `[module_main.c:CONFIG_EXAMPLES_MODULE_BUILTINFS]` - Configuration guard on `CONFIG_EXAMPLES_MODULE_BUILTINFS`
- `[module_main.c:CONFIG_FS_ROMFS]` - Configuration guard on `CONFIG_FS_ROMFS`

## Side Effects
- `[module_main.c:/dev/chardev]` - Opens or interacts with VFS/device path `/dev/chardev`
- `[module_main.c:/dev/ram0]` - Opens or interacts with VFS/device path `/dev/ram0`
- `[module_main.c:/mnt/cromfs]` - Opens or interacts with VFS/device path `/mnt/cromfs`
- `[module_main.c:/mnt/romfs]` - Opens or interacts with VFS/device path `/mnt/romfs`
- `[module_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[module_main.c:open]` - Opens device nodes or files via `open()`
- `[module_main.c:mount]` - Mounts filesystems via `mount()`
- `[module_main.c:insmod]` - Inserts loadable modules via `insmod()`
- `[module_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[module_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[module_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
