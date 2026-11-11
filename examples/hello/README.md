# hello

## Overview
"Hello, World!" example (`hello`). Enable the "Hello, World!" example

## Interface
- `[Kconfig:EXAMPLES_HELLO]` - Build configuration option `EXAMPLES_HELLO`
- `[Kconfig:EXAMPLES_HELLO_PROGNAME]` - Build configuration option `EXAMPLES_HELLO_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HELLO_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_HELLO_PROGNAME}`
- `[hello_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SCHED_USER_IDENTITY]` - Requires kernel/app configuration `SCHED_USER_IDENTITY`

## Side Effects
- `[hello_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
