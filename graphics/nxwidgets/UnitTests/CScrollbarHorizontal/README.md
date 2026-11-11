# `graphics/nxwidgets/UnitTests/CScrollbarHorizontal`

## Overview
Implements `graphics/nxwidgets/UnitTests/CScrollbarHorizontal` source and header components (`cscrollbarhorizontal_main.cxx`, `cscrollbarhorizontaltest.cxx`) in the NuttX application tree.

## Interface
- [Makefile:PROGNAME=cscrollbarhorizontal]
- [cscrollbarhorizontal_main.cxx:main]

## Invariants
- None

## Side Effects
- [cscrollbarhorizontal_main.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cscrollbarhorizontal_main.cxx:printf]: Writes formatted diagnostic, logging, or console output.
- [cscrollbarhorizontaltest.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [cscrollbarhorizontaltest.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cscrollbarhorizontaltest.cxx:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
