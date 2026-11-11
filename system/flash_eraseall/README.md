# `system/flash_eraseall`

## Overview
Provides FLASH Erase-all Command (`system/flash_eraseall`). Enable support for the FLASH eraseall tool.

## Interface
- [Makefile:PROGNAME=flash_eraseall]
- [Kconfig:CONFIG_SYSTEM_FLASH_ERASEALL]
- [flash_eraseall_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_FLASH_ERASEALL]: Build and feature compilation gated by `CONFIG_SYSTEM_FLASH_ERASEALL`.
- [Kconfig:depends on MTD]: Requires Kconfig dependency condition `MTD`.

## Side Effects
- [flash_eraseall_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
