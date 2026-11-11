# `graphics/nxwidgets/UnitTests/CRadioButton`

## Overview
Implements `graphics/nxwidgets/UnitTests/CRadioButton` source and header components (`cradiobutton_main.cxx`, `cradiobuttontest.cxx`) in the NuttX application tree.

## Interface
- [Makefile:PROGNAME=cradiobutton]
- [cradiobutton_main.cxx:main]

## Invariants
- None

## Side Effects
- [cradiobutton_main.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cradiobutton_main.cxx:printf]: Writes formatted diagnostic, logging, or console output.
- [cradiobuttontest.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [cradiobuttontest.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [cradiobuttontest.cxx:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
