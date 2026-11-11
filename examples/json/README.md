# json

## Overview
JSON example (`json`). An example for the netutils/json library.

## Interface
- `[Kconfig:EXAMPLES_JSON]` - Build configuration option `EXAMPLES_JSON`
- `[Makefile:PROGNAME]` - Registers application/module target `json`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `json`
- `[json_main.c:struct record]` - Structure definition `record`
- `[json_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NETUTILS_CJSON || NETUTILS_JSON]` - Requires kernel/app configuration `NETUTILS_CJSON || NETUTILS_JSON`

## Side Effects
- `[json_main.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[json_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
