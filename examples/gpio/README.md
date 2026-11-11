# gpio

## Overview
GPIO driver example (`gpio`). Enable the GPIO driver example

## Interface
- `[Kconfig:EXAMPLES_GPIO]` - Build configuration option `EXAMPLES_GPIO`
- `[Kconfig:EXAMPLES_GPIO_PROGNAME]` - Build configuration option `EXAMPLES_GPIO_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_GPIO_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_GPIO_PROGNAME}`
- `[gpio_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on DEV_GPIO]` - Requires kernel/app configuration `DEV_GPIO`
- `[gpio_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[gpio_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[gpio_main.c:open]` - Opens device nodes or files via `open()`
- `[gpio_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
