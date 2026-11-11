# `system/ptpd`

## Overview
Provides PTP daemon commands (`system/ptpd`). Enable 'ptpd' command to start the PTP daemon

## Interface
- [Makefile:PROGNAME=ptpd]
- [Kconfig:CONFIG_SYSTEM_PTPD]
- [Kconfig:CONFIG_SYSTEM_PTPD_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_PTPD_STACKSIZE]
- [ptpd_main.c:do_ptpd_stop]
- [ptpd_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_PTPD]: Build and feature compilation gated by `CONFIG_SYSTEM_PTPD`.
- [Kconfig:CONFIG_SYSTEM_PTPD_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_PTPD_PRIORITY`.
- [ptpd_main.c:CONFIG_NET_TIMESTAMP]: Conditional compilation gated by `CONFIG_NET_TIMESTAMP`.
- [ptpd_main.c:CONFIG_SCHED_TICKLESS]: Conditional compilation gated by `CONFIG_SCHED_TICKLESS`.

## Side Effects
- [ptpd_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
