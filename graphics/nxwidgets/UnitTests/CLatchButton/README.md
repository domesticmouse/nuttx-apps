# `graphics/nxwidgets/UnitTests/CLatchButton`

## Overview
Implements `graphics/nxwidgets/UnitTests/CLatchButton` source and header components (`clatchbutton_main.cxx`, `clatchbuttontest.cxx`) in the NuttX application tree.

## Interface
- [Makefile:PROGNAME=clatchbutton]
- [clatchbutton_main.cxx:main]

## Invariants
- None

## Side Effects
- [clatchbutton_main.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [clatchbutton_main.cxx:printf]: Writes formatted diagnostic, logging, or console output.
- [clatchbuttontest.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [clatchbuttontest.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [clatchbuttontest.cxx:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
