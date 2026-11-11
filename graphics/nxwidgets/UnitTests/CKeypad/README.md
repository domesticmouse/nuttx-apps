# `graphics/nxwidgets/UnitTests/CKeypad`

## Overview
Implements `graphics/nxwidgets/UnitTests/CKeypad` source and header components (`ckeypad_main.cxx`, `ckeypadtest.cxx`) in the NuttX application tree.

## Interface
- [Makefile:PROGNAME=ckeypad]
- [ckeypad_main.cxx:main]

## Invariants
- None

## Side Effects
- [ckeypad_main.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [ckeypad_main.cxx:printf]: Writes formatted diagnostic, logging, or console output.
- [ckeypadtest.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [ckeypadtest.cxx:connect]: Performs network socket creation, binding, or protocol I/O.
- [ckeypadtest.cxx:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
