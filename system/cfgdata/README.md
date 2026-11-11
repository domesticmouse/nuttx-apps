# `system/cfgdata`

## Overview
Provides Cfgdata Command (`system/cfgdata`). Enable support for the CFGDATA tool.

## Interface
- [Makefile:PROGNAME=cfgdata]
- [Kconfig:CONFIG_SYSTEM_CFGDATA]
- [Kconfig:CONFIG_SYSTEM_CFGDATA_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_CFGDATA_PRIORITY]
- [cfgdata_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_CFGDATA]: Build and feature compilation gated by `CONFIG_SYSTEM_CFGDATA`.
- [Kconfig:CONFIG_SYSTEM_CFGDATA_STACKSIZE]: Build and feature compilation gated by `CONFIG_SYSTEM_CFGDATA_STACKSIZE`.
- [Kconfig:depends on !MTD_CONFIG_NONE]: Requires Kconfig dependency condition `!MTD_CONFIG_NONE`.
- [cfgdata_main.c:CONFIG_MTD_CONFIG_NAMED]: Conditional compilation gated by `CONFIG_MTD_CONFIG_NAMED`.

## Side Effects
- [cfgdata_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [cfgdata_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [cfgdata_main.c:malloc]: Allocates or releases dynamic heap memory.
- [cfgdata_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
