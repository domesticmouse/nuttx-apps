# `graphics/nxwidgets/UnitTests/CGlyphButton`

## Overview
Implements `graphics/nxwidgets/UnitTests/CGlyphButton` source and header components (`cglyphbutton_main.cxx`, `cglyphbuttontest.cxx`) in the NuttX application tree.

## Interface
- [Makefile:PROGNAME=cglyphbutton]
- [cglyphbutton_main.cxx:main]

## Invariants
- None

## Side Effects
- [cglyphbutton_main.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cglyphbutton_main.cxx:printf]: Writes formatted diagnostic, logging, or console output.
- [cglyphbuttontest.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [cglyphbuttontest.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cglyphbuttontest.cxx:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
