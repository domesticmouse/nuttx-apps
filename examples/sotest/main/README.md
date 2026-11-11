# main

## Overview
Shared Library Example (`sotest/main`). Enable the shared library example

## Interface
- `[Kconfig:EXAMPLES_SOTEST]` - Build configuration option `EXAMPLES_SOTEST`
- `[Kconfig:EXAMPLES_SOTEST_BUILTINFS]` - Build configuration option `EXAMPLES_SOTEST_BUILTINFS`
- `[Makefile:PROGNAME]` - Registers application/module target `sotest`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `sotest`
- `[sotest_main.c:main]` - Application entry point `main()`
- `[mk_pkg_fixture_shared.c:struct sha256_state_s]` - Structure definition `sha256_state_s`
- `[mk_pkg_fixture_shared.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on LIBC_DLFCN]` - Requires kernel/app configuration `LIBC_DLFCN`
- `[Kconfig:depends on FS_ROMFS && BUILD_FLAT && BOARDCTL_ROMDISK]` - Requires kernel/app configuration `FS_ROMFS && BUILD_FLAT && BOARDCTL_ROMDISK`
- `[Kconfig:depends on EXPERIMENTAL]` - Requires kernel/app configuration `EXPERIMENTAL`
- `[sotest_main.c:#error]` - Compile-time precondition: You must select CONFIG_LIBC_DLFCN in your configuration file
- `[sotest_main.c:#error]` - Compile-time precondition: You must select CONFIG_FS_ROMFS in your configuration file
- `[sotest_main.c:#error]` - Compile-time precondition: You must not disable mountpoints via CONFIG_DISABLE_MOUNTPOINT in your configuration file
- `[sotest_main.c:CONFIG_EXAMPLES_SOTEST_BUILTINFS]` - Configuration guard on `CONFIG_EXAMPLES_SOTEST_BUILTINFS`
- `[sotest_main.c:CONFIG_LIBC_DLFCN]` - Configuration guard on `CONFIG_LIBC_DLFCN`
- `[sotest_main.c:CONFIG_FS_ROMFS]` - Configuration guard on `CONFIG_FS_ROMFS`
- `[sotest_main.c:CONFIG_DISABLE_MOUNTPOINT]` - Configuration guard on `CONFIG_DISABLE_MOUNTPOINT`
- `[sotest_main.c:argc]` - Validates command-line argument count `argc`
- `[mk_pkg_fixture_shared.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[sotest_main.c:/dev/ram%d]` - Opens or interacts with VFS/device path `/dev/ram%d`
- `[sotest_main.c:/mnt/sotest/romfs]` - Opens or interacts with VFS/device path `/mnt/sotest/romfs`
- `[sotest_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[sotest_main.c:mount]` - Mounts filesystems via `mount()`
- `[sotest_main.c:umount]` - Unmounts filesystems via `umount()`
- `[sotest_main.c:dlopen]` - Loads dynamic shared objects via `dlopen()`
- `[sotest_main.c:syslog]` - Writes diagnostic log entries via `syslog()`
- `[mk_pkg_fixture_shared.c:/etc/nxpkg/index.json\]` - Opens or interacts with VFS/device path `/etc/nxpkg/index.json\`
- `[mk_pkg_fixture_shared.c:fopen]` - Opens standard I/O file streams via `fopen()`

## Verification
- Run: `make test`
