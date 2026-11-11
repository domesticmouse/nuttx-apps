# wamr_module

## Overview
WAMR module example (`wamr_module`). This example demonstrates how to register a external module into WAMR runtime.

## Interface
- `[Kconfig:EXAMPLES_WAMR_MODULE]` - Build configuration option `EXAMPLES_WAMR_MODULE`
- `[module_hello.c:wamr_module_hello_register]` - Public function `wamr_module_hello_register()`

## Invariants
- None

## Side Effects
- `[module_hello.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
