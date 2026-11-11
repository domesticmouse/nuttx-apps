# zerocross

## Overview
Zero Cross Detection example (`zerocross`). Enable the zero cross detection example

## Interface
- `[Kconfig:EXAMPLES_ZEROCROSS]` - Build configuration option `EXAMPLES_ZEROCROSS`
- `[Kconfig:EXAMPLES_ZEROCROSS_DEVNAME]` - Build configuration option `EXAMPLES_ZEROCROSS_DEVNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `zerocross`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `zerocross`
- `[zerocross_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SENSORS_ZEROCROSS && ENABLE_ALL_SIGNALS]` - Requires kernel/app configuration `SENSORS_ZEROCROSS && ENABLE_ALL_SIGNALS`
- `[zerocross_main.c:#error]` - Compile-time precondition: CONFIG_SENSORS_ZEROCROSS is not defined in the configuration
- `[zerocross_main.c:CONFIG_SENSORS_ZEROCROSS]` - Configuration guard on `CONFIG_SENSORS_ZEROCROSS`
- `[zerocross_main.c:CONFIG_EXAMPLES_ZEROCROSS_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_ZEROCROSS_DEVNAME`
- `[zerocross_main.c:CONFIG_EXAMPLES_ZEROCROSS_SIGNO]` - Configuration guard on `CONFIG_EXAMPLES_ZEROCROSS_SIGNO`

## Side Effects
- `[zerocross_main.c:/dev/zc0]` - Opens or interacts with VFS/device path `/dev/zc0`
- `[zerocross_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[zerocross_main.c:open]` - Opens device nodes or files via `open()`
- `[zerocross_main.c:sigwaitinfo]` - Waits synchronously for signals via `sigwaitinfo()`
- `[zerocross_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
