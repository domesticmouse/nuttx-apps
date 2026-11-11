# uid

## Overview
UID/GID example (`uid`). Enable the UID/GID example

## Interface
- `[Kconfig:EXAMPLES_UID]` - Build configuration option `EXAMPLES_UID`
- `[Kconfig:EXAMPLES_UID_PROGNAME]` - Build configuration option `EXAMPLES_UID_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_UID_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_UID_PROGNAME}`
- `[uid_main.c:main]` - Application entry point `main()`

## Invariants
- `[uid_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[uid_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
