# `graphics/nxwidgets/UnitTests/CGlyphSliderHorizontal`

## Overview
Implements `graphics/nxwidgets/UnitTests/CGlyphSliderHorizontal` source and header components (`cglyphsliderhorizontal_main.cxx`, `cglyphsliderhorizontaltest.cxx`) in the NuttX application tree.

## Interface
- [Makefile:PROGNAME=cglyphsliderhorizontal]
- [cglyphsliderhorizontal_main.cxx:main]

## Invariants
- None

## Side Effects
- [cglyphsliderhorizontal_main.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cglyphsliderhorizontal_main.cxx:printf]: Writes formatted diagnostic, logging, or console output.
- [cglyphsliderhorizontaltest.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [cglyphsliderhorizontaltest.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cglyphsliderhorizontaltest.cxx:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
