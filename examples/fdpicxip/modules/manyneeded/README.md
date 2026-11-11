# manyneeded

## Overview
NuttX `fdpicxip/modules/manyneeded` component: A module whose DT_NEEDED list is longer than the loader follows.  The loader refuses it before it loads any of the libraries, so the module never runs.

## Interface
- `[Makefile:PROGNAME]` - Registers application/module target `manyneeded`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `manyneeded`
- `[manyneeded.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
