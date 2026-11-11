# main

## Overview
ELF Loader Example (`elf/main`). Enable the ELF loader example

## Interface
- `[Kconfig:EXAMPLES_ELF]` - Build configuration option `EXAMPLES_ELF`
- `[Kconfig:EXAMPLES_ELF_ROMFS]` - Build configuration option `EXAMPLES_ELF_ROMFS`
- `[Makefile:PROGNAME]` - Registers application/module target `elf`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `elf`
- `[elf_main.c:main]` - Application entry point `main()`
- `[mk_pkg_fixture.c:struct sha256_state_s]` - Structure definition `sha256_state_s`
- `[mk_pkg_fixture.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on ELF]` - Requires kernel/app configuration `ELF`
- `[Kconfig:depends on FS_ROMFS && BUILD_FLAT]` - Requires kernel/app configuration `FS_ROMFS && BUILD_FLAT`
- `[Kconfig:depends on FS_CROMFS && BUILD_FLAT]` - Requires kernel/app configuration `FS_CROMFS && BUILD_FLAT`
- `[elf_main.c:#error]` - Compile-time precondition: The binary loader is disabled (CONFIG_BINFMT_DISABLE)!
- `[elf_main.c:#error]` - Compile-time precondition: You must select CONFIG_ELF in your configuration file
- `[elf_main.c:#error]` - Compile-time precondition: You must not disable mountpoints via CONFIG_DISABLE_MOUNTPOINT in your configuration file
- `[elf_main.c:#error]` - Compile-time precondition: No file system selected
- `[elf_main.c:CONFIG_BINFMT_DISABLE]` - Configuration guard on `CONFIG_BINFMT_DISABLE`
- `[elf_main.c:CONFIG_ELF]` - Configuration guard on `CONFIG_ELF`
- `[elf_main.c:CONFIG_DISABLE_MOUNTPOINT]` - Configuration guard on `CONFIG_DISABLE_MOUNTPOINT`
- `[elf_main.c:CONFIG_EXAMPLES_ELF_DEVMINOR]` - Configuration guard on `CONFIG_EXAMPLES_ELF_DEVMINOR`
- `[mk_pkg_fixture.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[elf_main.c:/dev/ram%d]` - Opens or interacts with VFS/device path `/dev/ram%d`
- `[elf_main.c:/mnt/elf/]` - Opens or interacts with VFS/device path `/mnt/elf/`
- `[elf_main.c:/mnt/elf/cromfs]` - Opens or interacts with VFS/device path `/mnt/elf/cromfs`
- `[elf_main.c:/mnt/elf/romfs]` - Opens or interacts with VFS/device path `/mnt/elf/romfs`
- `[elf_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[elf_main.c:mount]` - Mounts filesystems via `mount()`
- `[elf_main.c:exec]` - Executes binary programs in-place via `exec()`
- `[elf_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[mk_pkg_fixture.c:/etc/nxpkg/index.json\]` - Opens or interacts with VFS/device path `/etc/nxpkg/index.json\`
- `[mk_pkg_fixture.c:fopen]` - Opens standard I/O file streams via `fopen()`

## Verification
- Run: `make test`
