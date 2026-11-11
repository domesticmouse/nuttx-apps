# watchdog

## Overview
Watchdog Timer example (`watchdog`). Enable the watchdog timer example

## Interface
- `[Kconfig:EXAMPLES_WATCHDOG]` - Build configuration option `EXAMPLES_WATCHDOG`
- `[Kconfig:EXAMPLES_WATCHDOG_DEVPATH]` - Build configuration option `EXAMPLES_WATCHDOG_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `wdog`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `wdog`
- `[watchdog_main.c:struct wdog_example_s]` - Structure definition `wdog_example_s`
- `[watchdog_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on WATCHDOG]` - Requires kernel/app configuration `WATCHDOG`
- `[watchdog.h:#error]` - Compile-time precondition: WATCHDOG device support is not enabled (CONFIG_WATCHDOG)
- `[watchdog.h:CONFIG_WATCHDOG]` - Configuration guard on `CONFIG_WATCHDOG`
- `[watchdog.h:CONFIG_EXAMPLES_WATCHDOG_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_WATCHDOG_DEVPATH`
- `[watchdog.h:CONFIG_EXAMPLES_WATCHDOG_PINGTIME]` - Configuration guard on `CONFIG_EXAMPLES_WATCHDOG_PINGTIME`
- `[watchdog.h:CONFIG_EXAMPLES_WATCHDOG_PINGDELAY]` - Configuration guard on `CONFIG_EXAMPLES_WATCHDOG_PINGDELAY`
- `[watchdog_main.c:CONFIG_DEBUG_WATCHDOG]` - Configuration guard on `CONFIG_DEBUG_WATCHDOG`

## Side Effects
- `[watchdog.h:/dev/watchdog0]` - Opens or interacts with VFS/device path `/dev/watchdog0`
- `[watchdog_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[watchdog_main.c:open]` - Opens device nodes or files via `open()`
- `[watchdog_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
