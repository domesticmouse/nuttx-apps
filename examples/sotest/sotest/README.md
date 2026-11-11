# sotest

## Overview
NuttX `sotest/sotest` component: Public Function Prototypes

## Interface
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `sotest`
- `[sotest.c:testfunc1]` - Public function `testfunc1()`
- `[sotest.c:testfunc2]` - Public function `testfunc2()`
- `[sotest.c:testfunc3]` - Public function `testfunc3()`

## Invariants
- `[sotest.c:CONFIG_LIBC_ELF_MAXDEPEND]` - Configuration guard on `CONFIG_LIBC_ELF_MAXDEPEND`

## Side Effects
- None

## Verification
- Run: `make test`
