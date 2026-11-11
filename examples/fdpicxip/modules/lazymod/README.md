# lazymod

## Overview
NuttX `fdpicxip/modules/lazymod` component: Built without -mlong-calls and linked with -z lazy (see the Makefile), so its imported function descriptors land in DT_JMPREL instead of DT_REL.

## Interface
- `[Makefile:PROGNAME]` - Registers application/module target `lazymod`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `lazymod`
- `[lazymod.c:main]` - Application entry point `main()`

## Invariants
- `[lazymod.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[lazymod.c:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
