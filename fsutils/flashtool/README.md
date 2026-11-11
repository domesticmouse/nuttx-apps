# Flash Tool Command (`fsutils/flashtool`)

## Overview
Implements the interactive/command-line `flashtool` built-in utility (`CONFIG_FSUTILS_FLASHTOOL`) for querying geometry, reading, writing, and erasing sectors on MTD flash devices exposed via block-to-character (`BCH`) drivers.

## Interface
- `[flashtool_main.c:main]`: CLI entry point (`flashtool`) parsing flash operation flags and executing MTD/BCH device operations.
- `[flashtool_main.c:enum opr_list]`: Enumeration of supported flash operations (read, write, erase).
- `[Kconfig:FSUTILS_FLASHTOOL]`, `[Kconfig:FSUTILS_FLASHTOOL_STACKSIZE]`, `[Kconfig:FSUTILS_FLASHTOOL_PRIORITY]`: Build configuration symbols.

## Invariants
- `[Kconfig:FSUTILS_FLASHTOOL]`: Depends on `MTD` and `BCH`.

## Side Effects
- `[flashtool_main.c:main]`: Opens flash device paths, allocates transfer buffers via `malloc`, issues `MTDIOC_*` `ioctl` calls, reads/writes flash contents, and prints status output via `printf`.

## Verification
- Run: `make test`
