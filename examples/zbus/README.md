# zbus

## Overview
ZBus example (`zbus`). Enable the zbus message bus example.

## Interface
- `[Kconfig:EXAMPLES_ZBUS]` - Build configuration option `EXAMPLES_ZBUS`
- `[Kconfig:EXAMPLES_ZBUS_PROGNAME]` - Build configuration option `EXAMPLES_ZBUS_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_ZBUS_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_ZBUS_PROGNAME}`
- `[zbus_main.c:struct acc_msg]` - Structure definition `acc_msg`
- `[zbus_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on ZBUS]` - Requires kernel/app configuration `ZBUS`

## Side Effects
- `[zbus_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[zbus_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
