# `graphics/nxwidgets/UnitTests/CButton`

## Overview
Implements `graphics/nxwidgets/UnitTests/CButton` source and header components (`cbutton_main.cxx`, `cbuttontest.cxx`) in the NuttX application tree.

## Interface
- [Makefile:PROGNAME=cbutton]
- [cbutton_main.cxx:main]

## Invariants
- None

## Side Effects
- [cbutton_main.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cbutton_main.cxx:printf]: Writes formatted diagnostic, logging, or console output.
- [cbuttontest.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [cbuttontest.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cbuttontest.cxx:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
