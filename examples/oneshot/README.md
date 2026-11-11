# oneshot

## Overview
Oneshot timer example (`oneshot`). Enable the oneshot timer driver example

## Interface
- `[Kconfig:EXAMPLES_ONESHOT]` - Build configuration option `EXAMPLES_ONESHOT`
- `[Kconfig:EXAMPLES_ONESHOT_DEVNAME]` - Build configuration option `EXAMPLES_ONESHOT_DEVNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_ONESHOT_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_ONESHOT_PROGNAME}`
- `[oneshot_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on ONESHOT && ENABLE_ALL_SIGNALS]` - Requires kernel/app configuration `ONESHOT && ENABLE_ALL_SIGNALS`
- `[oneshot_main.c:CONFIG_EXAMPLES_ONESHOT_DEVNAME]` - Configuration guard on `CONFIG_EXAMPLES_ONESHOT_DEVNAME`
- `[oneshot_main.c:CONFIG_EXAMPLES_ONESHOT_DELAY]` - Configuration guard on `CONFIG_EXAMPLES_ONESHOT_DELAY`
- `[oneshot_main.c:CONFIG_EXAMPLES_ONESHOT_SIGNO]` - Configuration guard on `CONFIG_EXAMPLES_ONESHOT_SIGNO`
- `[oneshot_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[oneshot_main.c:/dev/oneshot]` - Opens or interacts with VFS/device path `/dev/oneshot`
- `[oneshot_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[oneshot_main.c:open]` - Opens device nodes or files via `open()`
- `[oneshot_main.c:sigwaitinfo]` - Waits synchronously for signals via `sigwaitinfo()`
- `[oneshot_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
