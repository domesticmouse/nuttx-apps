# hello_wasm

## Overview
"Hello, WebAssembly!" example (`hello_wasm`). Enable the "Hello, WebAssembly!" example

## Interface
- `[Kconfig:EXAMPLES_HELLO_WASM]` - Build configuration option `EXAMPLES_HELLO_WASM`
- `[Kconfig:EXAMPLES_HELLO_WASM_PROGNAME]` - Build configuration option `EXAMPLES_HELLO_WASM_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HELLO_WASM_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_HELLO_WASM_PROGNAME}`
- `[hello_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[hello_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
