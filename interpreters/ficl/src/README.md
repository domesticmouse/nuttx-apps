# `interpreters/ficl/src`

## Overview
Implements `interpreters/ficl/src` source and header components (`nuttx.c`, `nuttx.h`) in the NuttX application tree.

## Interface
- [nuttx.h:ficlInteger8]
- [nuttx.h:ficlUnsigned8]
- [nuttx.h:ficlInteger16]
- [nuttx.h:ficlUnsigned16]
- [nuttx.h:ficlInteger32]
- [nuttx.h:ficlUnsigned32]
- [nuttx.h:ficlInteger]
- [nuttx.h:ficlUnsigned]
- [nuttx.h:ficlFloat]
- [nuttx.h:FICL_PLATFORM_BASIC_TYPES]
- [nuttx.h:FICL_PLATFORM_HAS_2INTEGER]
- [nuttx.h:FICL_PLATFORM_HAS_FTRUNCATE]
- [nuttx.h:FICL_PLATFORM_OS]
- [nuttx.h:FICL_PLATFORM_ARCHITECTURE]
- [nuttx.c:ficlMalloc]
- [nuttx.c:ficlRealloc]
- [nuttx.c:ficlFree]
- [nuttx.c:ficlCallbackDefaultTextOut]

## Invariants
- None

## Side Effects
- [nuttx.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
