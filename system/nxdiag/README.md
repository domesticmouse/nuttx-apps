# `system/nxdiag`

## Overview
Provides System information and diagnostic (nxdiag) (`system/nxdiag`). Enable the nxdiag application to gather and display host and target system information. It can also perform some

## Interface
- [Makefile:PROGNAME=nxdiag]
- [Kconfig:CONFIG_SYSTEM_NXDIAG]
- [Kconfig:CONFIG_SYSTEM_NXDIAG_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_NXDIAG_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_NXDIAG_CONF]
- [nxdiag.c:search_str_in_arr]
- [nxdiag.c:are_valid_args]
- [nxdiag.c:print_array]
- [nxdiag.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXDIAG]: Build and feature compilation gated by `CONFIG_SYSTEM_NXDIAG`.
- [Kconfig:CONFIG_SYSTEM_NXDIAG_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_NXDIAG_PRIORITY`.
- [Kconfig:depends on ARCH_CHIP_ESP32 || ARCH_CHIP_ESP32S2 || ARCH_CHIP_ESP32S3 || ARCH_CHIP_ESP32C3 || ARCH_CHIP_ESP32C6 || ARCH_CHIP_ESP32H2]: Requires Kconfig dependency condition `ARCH_CHIP_ESP32 || ARCH_CHIP_ESP32S2 || ARCH_CHIP_ESP32S3 || ARCH_CHIP_ESP32C3 || ARCH_CHIP_ESP32C6 || ARCH_CHIP_ESP32H2`.
- [Kconfig:depends on SYSTEM_NXDIAG_ESPRESSIF_CHIP]: Requires Kconfig dependency condition `SYSTEM_NXDIAG_ESPRESSIF_CHIP`.
- [nxdiag.c:CONFIG_SYSTEM_NXDIAG_ESPRESSIF_CHIP_WO_TOOL]: Conditional compilation gated by `CONFIG_SYSTEM_NXDIAG_ESPRESSIF_CHIP_WO_TOOL`.
- [nxdiag.c:CONFIG_SYSTEM_NXDIAG_COMP_FLAGS]: Conditional compilation gated by `CONFIG_SYSTEM_NXDIAG_COMP_FLAGS`.

## Side Effects
- [nxdiag.c:open]: Performs VFS file or device descriptor I/O operations.
- [nxdiag.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
