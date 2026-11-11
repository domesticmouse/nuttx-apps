# user

## Overview
NuttX `fdpicxip/modules/user` component: Uses libcounter.so.  Two instances run concurrently.  Each instance is a task group with its own copy of the library data, so its total counts its own bumps.  The library text is shared. libcounter is also a *leaf* library -- it calls nothing outside itself, so it has no PLT and therefore no DT_PLTG

## Interface
- `[Makefile:PROGNAME]` - Registers application/module target `user`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `user`
- `[user.c:main]` - Application entry point `main()`

## Invariants
- `[user.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[user.c:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
