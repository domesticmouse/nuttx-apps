# `system/hexed/include`

## Overview
Implements `system/hexed/include` source and header components (`bfile.h`, `cmdargs.h`, `hexed.h`) in the NuttX application tree.

## Interface
- [bfile.h:struct bfile_s]
- [bfile.h:fsize]
- [bfile.h:bfflush]
- [bfile.h:bfopen]
- [bfile.h:bfclose]
- [bfile.h:bfclip]
- [bfile.h:bfcopy]
- [bfile.h:bfinsert]
- [bfile.h:bfmove]
- [bfile.h:bfread]
- [bfile.h:bftruncate]
- [bfile.h:bfwrite]
- [bfile.h:BFILE_BUF_MIN]
- [bfile.h:BFILE_BUF_ALIGN]
- [bfile.h:BFILE_FL_DIRTY]
- [cmdargs.h:struct arglist_s]
- [cmdargs.h:struct cmdargs_s]
- [cmdargs.h:parsecmdargs]

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
