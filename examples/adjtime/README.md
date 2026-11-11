# adjtime

## Overview
Ajdtime function example (`adjtime`). Enable the adjtime example. This application demonstrates the usage of adjtime() interface used to synchronize system clock time if its value varies from real time (usually get by external RTC).

## Interface
- `[Kconfig:EXAMPLES_ADJTIME]` - Build configuration option `EXAMPLES_ADJTIME`
- `[Kconfig:EXAMPLES_ADJTIME_PROGNAME]` - Build configuration option `EXAMPLES_ADJTIME_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_ADJTIME_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_ADJTIME_PROGNAME}`
- `[adjtime_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on CLOCK_ADJTIME]` - Requires kernel/app configuration `CLOCK_ADJTIME`

## Side Effects
- `[adjtime_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
