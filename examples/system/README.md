# system

## Overview
System() example (`system`). Enable the system() example

## Interface
- `[Kconfig:EXAMPLES_SYSTEM]` - Build configuration option `EXAMPLES_SYSTEM`
- `[Kconfig:EXAMPLES_SYSTEM_PROGNAME]` - Build configuration option `EXAMPLES_SYSTEM_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SYSTEM_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_SYSTEM_PROGNAME}`
- `[system_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SYSTEM_SYSTEM]` - Requires kernel/app configuration `SYSTEM_SYSTEM`

## Side Effects
- `[system_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
