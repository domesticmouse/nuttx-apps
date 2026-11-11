# tiff

## Overview
TIFF file generation example (`tiff`). Enable the TIFF file generation example

## Interface
- `[Kconfig:EXAMPLES_TIFF]` - Build configuration option `EXAMPLES_TIFF`
- `[Makefile:PROGNAME]` - Registers application/module target `tiff`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `tiff`
- `[tiff_main.c:main]` - Application entry point `main()`

## Invariants
- `[tiff_main.c:CONFIG_EXAMPLES_TIFF_OUTFILE]` - Configuration guard on `CONFIG_EXAMPLES_TIFF_OUTFILE`
- `[tiff_main.c:CONFIG_EXAMPLES_TIFF_TMPFILE1]` - Configuration guard on `CONFIG_EXAMPLES_TIFF_TMPFILE1`
- `[tiff_main.c:CONFIG_EXAMPLES_TIFF_TMPFILE2]` - Configuration guard on `CONFIG_EXAMPLES_TIFF_TMPFILE2`

## Side Effects
- `[tiff_main.c:/tmp/result.tif]` - Opens or interacts with VFS/device path `/tmp/result.tif`
- `[tiff_main.c:/tmp/tmpfile1.dat]` - Opens or interacts with VFS/device path `/tmp/tmpfile1.dat`
- `[tiff_main.c:/tmp/tmpfile2.dat]` - Opens or interacts with VFS/device path `/tmp/tmpfile2.dat`
- `[tiff_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
