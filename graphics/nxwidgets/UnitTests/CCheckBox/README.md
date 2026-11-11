# `graphics/nxwidgets/UnitTests/CCheckBox`

## Overview
Implements `graphics/nxwidgets/UnitTests/CCheckBox` source and header components (`ccheckbox_main.cxx`, `ccheckboxtest.cxx`) in the NuttX application tree.

## Interface
- [Makefile:PROGNAME=ccheckbox]
- [ccheckbox_main.cxx:main]

## Invariants
- None

## Side Effects
- [ccheckbox_main.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [ccheckbox_main.cxx:printf]: Writes formatted diagnostic, logging, or console output.
- [ccheckboxtest.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [ccheckboxtest.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [ccheckboxtest.cxx:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
