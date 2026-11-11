# Platform Dummy Source (`platform/dummy`)

## Overview
Provides a fallback empty translation unit (`dummy.c`) compiled into the platform archive (`apps/platform`) when no board-specific platform directory is linked, preventing archive creation failures on toolchains that reject empty static libraries.

## Interface
- `[Make.defs:CSRCS]`: Appends `dummy.c` to the platform library `CSRCS` list.

## Invariants
- None

## Side Effects
- `[Make.defs:CSRCS]`: Ensures at least one object file (`dummy.o`) is included when archiving `apps/platform`.

## Verification
- Run: `make test`
