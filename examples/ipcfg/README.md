# ipcfg

## Overview
IP Configuration file example (`ipcfg`). Enable the IP Configuration file example

## Interface
- `[Kconfig:EXAMPLES_IPCFG]` - Build configuration option `EXAMPLES_IPCFG`
- `[Kconfig:EXAMPLES_IPCFG_PROGNAME]` - Build configuration option `EXAMPLES_IPCFG_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_IPCFG_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_IPCFG_PROGNAME}`
- `[ipcfg_main.c:ipcfg_dump_file]` - Public function `ipcfg_dump_file()`
- `[ipcfg_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on FSUTILS_IPCFG]` - Requires kernel/app configuration `FSUTILS_IPCFG`
- `[ipcfg_main.c:#error]` - Compile-time precondition: This example will not work with a character device
- `[ipcfg_main.c:CONFIG_IPCFG_CHARDEV]` - Configuration guard on `CONFIG_IPCFG_CHARDEV`
- `[ipcfg_main.c:CONFIG_IPCFG_WRITABLE]` - Configuration guard on `CONFIG_IPCFG_WRITABLE`
- `[ipcfg_main.c:CONFIG_NET_IP]` - Configuration guard on `CONFIG_NET_IP`
- `[ipcfg_main.c:CONFIG_IPCFG_BINARY]` - Configuration guard on `CONFIG_IPCFG_BINARY`

## Side Effects
- `[ipcfg_main.c:open]` - Opens device nodes or files via `open()`
- `[ipcfg_main.c:mount]` - Mounts filesystems via `mount()`
- `[ipcfg_main.c:umount]` - Unmounts filesystems via `umount()`
- `[ipcfg_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[ipcfg_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[ipcfg_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
