# posix_spawn

## Overview
posix_spawn Unit Test (`posix_spawn`). Enable the posix_spawn() unit test

## Interface
- `[Kconfig:EXAMPLES_POSIXSPAWN]` - Build configuration option `EXAMPLES_POSIXSPAWN`
- `[Kconfig:EXAMPLES_POSIXSPAWN_DEVMINOR]` - Build configuration option `EXAMPLES_POSIXSPAWN_DEVMINOR`
- `[Makefile:PROGNAME]` - Registers application/module target `posix_spawn`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `posix_spawn`
- `[spawn_main.c:main]` - Application entry point `main()`
- **filesystem**: [`./filesystem/README.md`](./filesystem/README.md) - Intermediate grouping directory for `posix_spawn/filesystem`, organizing submodules: hello, redirect.

## Invariants
- `[Kconfig:depends on !BINFMT_DISABLE]` - Requires kernel/app configuration `!BINFMT_DISABLE`
- `[Kconfig:depends on !DISABLE_MOUNTPOINT]` - Requires kernel/app configuration `!DISABLE_MOUNTPOINT`
- `[Kconfig:depends on BOARDCTL]` - Requires kernel/app configuration `BOARDCTL`
- `[spawn_main.c:CONFIG_EXAMPLES_POSIXSPAWN_DEVMINOR]` - Configuration guard on `CONFIG_EXAMPLES_POSIXSPAWN_DEVMINOR`
- `[spawn_main.c:CONFIG_EXAMPLES_POSIXSPAWN_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_POSIXSPAWN_DEVPATH`
- `[spawn_main.c:CONFIG_DEBUG_FEATURES]` - Configuration guard on `CONFIG_DEBUG_FEATURES`
- `[spawn_main.c:CONFIG_LIBC_ENVPATH]` - Configuration guard on `CONFIG_LIBC_ENVPATH`

## Side Effects
- `[spawn_main.c:/dev/ram0]` - Opens or interacts with VFS/device path `/dev/ram0`
- `[spawn_main.c:/mnt/romfs]` - Opens or interacts with VFS/device path `/mnt/romfs`
- `[spawn_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[spawn_main.c:posix_spawn]` - Spawns child processes via `posix_spawn()`
- `[spawn_main.c:mount]` - Mounts filesystems via `mount()`
- `[spawn_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
