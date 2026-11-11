# leds

## Overview
LED driver example (`leds`). Enable the LED driversexample

## Interface
- `[Kconfig:EXAMPLES_LEDS]` - Build configuration option `EXAMPLES_LEDS`
- `[Kconfig:EXAMPLES_LEDS_PROGNAME]` - Build configuration option `EXAMPLES_LEDS_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LEDS_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_LEDS_PROGNAME}`
- `[leds_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on USERLED]` - Requires kernel/app configuration `USERLED`

## Side Effects
- `[leds_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[leds_main.c:open]` - Opens device nodes or files via `open()`
- `[leds_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[leds_main.c:sigaction]` - Registers signal handlers via `sigaction()`
- `[leds_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
