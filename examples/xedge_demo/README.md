# xedge_demo

## Overview
Xedge IoT Toolkit Demo (`xedge_demo`). Simple demonstration of the Xedge IoT Toolkit library.

## Interface
- `[Kconfig:EXAMPLES_XEDGE_DEMO]` - Build configuration option `EXAMPLES_XEDGE_DEMO`
- `[Kconfig:EXAMPLES_XEDGE_DEMO_PROGNAME]` - Build configuration option `EXAMPLES_XEDGE_DEMO_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_XEDGE_DEMO_PROGNAME)`
- `[xedge_main.c:xedgeInitDiskIo]` - Public function `xedgeInitDiskIo()`
- `[xedge_main.c:xedgeOpenAUX]` - Public function `xedgeOpenAUX()`
- `[xedge_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NETUTILS_XEDGE && ALLOW_GPL_COMPONENTS && ENABLE_ALL_SIGNALS]` - Requires kernel/app configuration `NETUTILS_XEDGE && ALLOW_GPL_COMPONENTS && ENABLE_ALL_SIGNALS`

## Side Effects
- `[xedge_main.c:/mnt/lfs]` - Opens or interacts with VFS/device path `/mnt/lfs`
- `[xedge_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[xedge_main.c:syslog]` - Writes diagnostic log entries via `syslog()`
- `[xedge_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
