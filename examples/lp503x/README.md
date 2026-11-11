# lp503x

## Overview
LP503X PWM LED example (`lp503x`). Enable the LP503X example

## Interface
- `[Kconfig:EXAMPLES_LP503X]` - Build configuration option `EXAMPLES_LP503X`
- `[Kconfig:EXAMPLES_LP503X_PROGNAME]` - Build configuration option `EXAMPLES_LP503X_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_LP503X_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_LP503X_PROGNAME}`
- `[lp503x_main.c:struct lp503x_cmd_s]` - Structure definition `lp503x_cmd_s`
- `[lp503x_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on LP503X]` - Requires kernel/app configuration `LP503X`
- `[lp503x_main.c:CONFIG_SYSTEM_SYSTEM]` - Configuration guard on `CONFIG_SYSTEM_SYSTEM`

## Side Effects
- `[lp503x_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[lp503x_main.c:open]` - Opens device nodes or files via `open()`
- `[lp503x_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
