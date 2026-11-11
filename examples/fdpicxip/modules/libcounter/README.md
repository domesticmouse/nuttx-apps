# libcounter

## Overview
NuttX `fdpicxip/modules/libcounter` component: A shared library with its own state. g_calls is the interesting part: it lives in the library's writable segment.  Each task group that names this library in DT_NEEDED loads its own instance, so each has its own g_calls.  The library's code is mapped once and executed in place.

## Interface
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `libcounter`
- `[libcounter.c:counter_bump]` - Public function `counter_bump()`
- `[libcounter.c:counter_total]` - Public function `counter_total()`

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
