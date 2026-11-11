# `system/lsan`

## Overview
Provides lsan memory leak detection (`system/lsan`). Alsans support for the LeakSanitizer (lsan) memory leak detection tool.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_LSAN_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_LSAN]
- [Kconfig:CONFIG_SYSTEM_LSAN_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_LSAN_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_LSAN_STACKSIZE]
- [lsan_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_LSAN]: Build and feature compilation gated by `CONFIG_SYSTEM_LSAN`.
- [Kconfig:CONFIG_SYSTEM_LSAN_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_LSAN_PROGNAME`.
- [Kconfig:depends on SIM_ASAN]: Requires Kconfig dependency condition `SIM_ASAN`.

## Side Effects
- None

## Verification
- Run: `make test`
