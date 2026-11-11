# `system/hexed/src`

## Overview
Implements `system/hexed/src`: Parse the command line arguments Input parameters:

## Interface
- [bfile.c:fsize]
- [bfile.c:bftruncate]
- [bfile.c:bfflush]
- [bfile.c:bfopen]
- [bfile.c:bfclose]
- [bfile.c:bfclip]
- [bfile.c:bfinsert]
- [bfile.c:bfcopy]
- [bfile.c:bfmove]
- [bfile.c:bfread]
- [bfile.c:bfwrite]
- [cmdargs.c:parsecmdargs]
- [hexcopy.c:hexcopy]
- [hexdump.c:hexdump]
- [hexed.c:hexed_fatal]
- [hexed.c:loadfile]
- [hexed.c:savefile]
- [hexed.c:hexcmd]

## Invariants
- None

## Side Effects
- [bfile.c:fwrite]: Performs VFS file or device descriptor I/O operations.
- [bfile.c:realloc]: Allocates or releases dynamic heap memory.
- [bfile.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [hexdump.c:printf]: Writes formatted diagnostic, logging, or console output.
- [hexed.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [hexenter.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
