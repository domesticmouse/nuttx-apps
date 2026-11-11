# mld

## Overview
MLD example (`mld`). Enable the MLD example

## Interface
- `[Kconfig:EXAMPLES_MLD]` - Build configuration option `EXAMPLES_MLD`
- `[Kconfig:EXAMPLES_MLD_PROGNAME]` - Build configuration option `EXAMPLES_MLD_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MLD_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MLD_PROGNAME}`
- `[mld_main.c:mld_catfile]` - Public function `mld_catfile()`
- `[mld_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_UDP && NET_MLD]` - Requires kernel/app configuration `NET_UDP && NET_MLD`
- `[mld_main.c:CONFIG_DISABLE_MOUNTPOINT]` - Configuration guard on `CONFIG_DISABLE_MOUNTPOINT`
- `[mld_main.c:CONFIG_NET_STATISTICS]` - Configuration guard on `CONFIG_NET_STATISTICS`
- `[mld_main.c:CONFIG_NET_ROUTE]` - Configuration guard on `CONFIG_NET_ROUTE`
- `[mld_main.c:CONFIG_EXAMPLES_MLD_INIT]` - Configuration guard on `CONFIG_EXAMPLES_MLD_INIT`

## Side Effects
- `[mld_main.c:/proc/net/mld]` - Opens or interacts with VFS/device path `/proc/net/mld`
- `[mld_main.c:/proc/net/route/ipv6]` - Opens or interacts with VFS/device path `/proc/net/route/ipv6`
- `[mld_main.c:open]` - Opens device nodes or files via `open()`
- `[mld_main.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[mld_main.c:sendto]` - Sends datagram packets via `sendto()`
- `[mld_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[mld_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[mld_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
