# `system/hex2bin`

## Overview
Provides Intel HEX to binary conversion (`system/hex2bin`). Enable support for a logic to convert Intel HEX format to binary.

## Interface
- [Makefile:PROGNAME=hex2bin]
- [Makefile:PROGNAME=hex2mem]
- [Kconfig:CONFIG_SYSTEM_HEX2BIN]
- [Kconfig:CONFIG_SYSTEM_HEX2BIN_BUILTIN]
- [Kconfig:CONFIG_SYSTEM_HEX2BIN_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_HEX2BIN_PRIORITY]
- [hex2bin_main.c:main]
- [hex2mem_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_HEX2BIN]: Build and feature compilation gated by `CONFIG_SYSTEM_HEX2BIN`.
- [Kconfig:CONFIG_SYSTEM_HEX2BIN_BUILTIN]: Build and feature compilation gated by `CONFIG_SYSTEM_HEX2BIN_BUILTIN`.
- [hex2bin_main.c:DEBUGASSERT]: Enforces `DEBUGASSERT(errcode > 0)` precondition.
- [hex2bin_main.c:CONFIG_SYSTEM_HEX2BIN_BUILTIN]: Conditional compilation gated by `CONFIG_SYSTEM_HEX2BIN_BUILTIN`.
- [hex2bin_main.c:CONFIG_SYSTEM_HEX2BIN_USAGE]: Conditional compilation gated by `CONFIG_SYSTEM_HEX2BIN_USAGE`.
- [hex2mem_main.c:DEBUGASSERT]: Enforces `DEBUGASSERT(errcode > 0)` precondition.

## Side Effects
- [hex2bin_main.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [hex2bin_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [hex2mem_main.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [hex2mem_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
