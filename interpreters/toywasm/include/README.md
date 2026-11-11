# `interpreters/toywasm/include`

## Overview
Implements `interpreters/toywasm/include` source and header components (`toywasm_config.h`, `toywasm_version.h`) in the NuttX application tree.

## Interface
- [toywasm_config.h:TOYWASM_USE_SEPARATE_EXECUTE]
- [toywasm_config.h:TOYWASM_USE_TAILCALL]
- [toywasm_config.h:TOYWASM_SORT_EXPORTS]
- [toywasm_config.h:TOYWASM_USE_JUMP_BINARY_SEARCH]
- [toywasm_config.h:TOYWASM_JUMP_CACHE2_SIZE]
- [toywasm_config.h:TOYWASM_USE_LOCALS_FAST_PATH]
- [toywasm_config.h:TOYWASM_USE_LOCALS_CACHE]
- [toywasm_config.h:TOYWASM_USE_SEPARATE_LOCALS]
- [toywasm_config.h:TOYWASM_USE_SMALL_CELLS]
- [toywasm_config.h:TOYWASM_USE_RESULTTYPE_CELLIDX]
- [toywasm_config.h:TOYWASM_USE_LOCALTYPE_CELLIDX]
- [toywasm_config.h:TOYWASM_ENABLE_HEAP_TRACKING]
- [toywasm_config.h:TOYWASM_ENABLE_HEAP_TRACKING_PEAK]
- [toywasm_config.h:TOYWASM_ENABLE_WRITER]
- [toywasm_config.h:TOYWASM_ENABLE_WASM_SIMD]
- [toywasm_config.h:TOYWASM_ENABLE_WASM_EXCEPTION_HANDLING]

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
