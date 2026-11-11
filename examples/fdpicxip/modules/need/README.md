# need

## Overview
NuttX `fdpicxip/modules/need` component: A stub library.  Only its name matters, as an entry in DT_NEEDED.

## Interface
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `need${n}`
- `[need.c:need_stub]` - Public function `need_stub()`

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
