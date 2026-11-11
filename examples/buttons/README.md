# buttons

## Overview
Buttons driver example (`buttons`). Enable the Buttons drivers example

## Interface
- `[Kconfig:EXAMPLES_BUTTONS]` - Build configuration option `EXAMPLES_BUTTONS`
- `[Kconfig:EXAMPLES_BUTTONS_PROGNAME]` - Build configuration option `EXAMPLES_BUTTONS_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_BUTTONS_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_BUTTONS_PROGNAME}`
- `[buttons_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on INPUT_BUTTONS]` - Requires kernel/app configuration `INPUT_BUTTONS`
- `[buttons_main.c:#error]` - Compile-time precondition: CONFIG_INPUT_BUTTONS is not defined in the configuration
- `[buttons_main.c:#error]` - Compile-time precondition: CONFIG_EXAMPLES_BUTTONS_QTD > 8
- `[buttons_main.c:CONFIG_INPUT_BUTTONS]` - Configuration guard on `CONFIG_INPUT_BUTTONS`
- `[buttons_main.c:CONFIG_INPUT_BUTTONS_NPOLLWAITERS]` - Configuration guard on `CONFIG_INPUT_BUTTONS_NPOLLWAITERS`
- `[buttons_main.c:CONFIG_EXAMPLES_BUTTONS_SIGNO]` - Configuration guard on `CONFIG_EXAMPLES_BUTTONS_SIGNO`
- `[buttons_main.c:CONFIG_INPUT_BUTTONS_POLL_DELAY]` - Configuration guard on `CONFIG_INPUT_BUTTONS_POLL_DELAY`

## Side Effects
- `[buttons_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[buttons_main.c:open]` - Opens device nodes or files via `open()`
- `[buttons_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[buttons_main.c:sigwaitinfo]` - Waits synchronously for signals via `sigwaitinfo()`
- `[buttons_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[buttons_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
