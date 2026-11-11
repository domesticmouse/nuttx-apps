# cpuhog

## Overview
CPU hog (`cpuhog`). Enable the cpuhog example

## Interface
- `[Kconfig:EXAMPLES_CPUHOG]` - Build configuration option `EXAMPLES_CPUHOG`
- `[Kconfig:EXAMPLES_CPUHOG_STACKSIZE]` - Build configuration option `EXAMPLES_CPUHOG_STACKSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `cpuhog`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `cpuhog`
- `[cpuhog_main.c:struct state_s]` - Structure definition `state_s`
- `[cpuhog_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on PIPES]` - Requires kernel/app configuration `PIPES`
- `[cpuhog_main.c:DEBUGASSERT]` - Runtime state and non-null pointer assertions via `DEBUGASSERT()`

## Side Effects
- `[cpuhog_main.c:/dev/cpuhogfifo]` - Opens or interacts with VFS/device path `/dev/cpuhogfifo`
- `[cpuhog_main.c:open]` - Opens device nodes or files via `open()`
- `[cpuhog_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[cpuhog_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[cpuhog_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
