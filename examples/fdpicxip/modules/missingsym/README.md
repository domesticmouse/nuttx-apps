# missingsym

## Overview
NuttX `fdpicxip/modules/missingsym` component: A module that imports a firmware symbol which does not exist.  It links cleanly -- the symbol simply becomes an undefined import resolved at load -- so the loader is the only thing that can catch it, when resolution fails rather than at link time.

## Interface
- `[Makefile:PROGNAME]` - Registers application/module target `missingsym`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `missingsym`
- `[missingsym.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
