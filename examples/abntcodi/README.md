# abntcodi

## Overview
ABNT CODI example (`abntcodi`). Enable the ABNT CODI test example

## Interface
- `[Kconfig:EXAMPLES_ABNTCODI]` - Build configuration option `EXAMPLES_ABNTCODI`
- `[Kconfig:EXAMPLES_ABNTCODI_PROGNAME]` - Build configuration option `EXAMPLES_ABNTCODI_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_ABNTCODI_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_ABNTCODI_PROGNAME}`
- `[abntcodi_main.c:print_abnt_codi]` - Public function `print_abnt_codi()`
- `[abntcodi_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[abntcodi_main.c:/dev/ttyS1]` - Opens or interacts with VFS/device path `/dev/ttyS1`
- `[abntcodi_main.c:open]` - Opens device nodes or files via `open()`
- `[abntcodi_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[abntcodi_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
