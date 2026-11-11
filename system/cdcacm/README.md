# `system/cdcacm`

## Overview
Provides USB CDC/ACM Device Commands (`system/cdcacm`). Enable the USB CDC/ACM class controls. These controls include:

## Interface
- [Makefile:PROGNAME=sercon]
- [Kconfig:CONFIG_SYSTEM_CDCACM]
- [Kconfig:CONFIG_SYSTEM_CDCACM_DEVMINOR]
- [Kconfig:CONFIG_SYSTEM_CDCACM_TRACEINIT]
- [Kconfig:CONFIG_SYSTEM_CDCACM_TRACECLASS]
- [cdcacm.h:CONFIG_SYSTEM_CDCACM_DEVMINOR]
- [cdcacm.h:TRACE_INIT_BITS]
- [cdcacm.h:TRACE_ERROR_BITS]
- [cdcacm.h:TRACE_CLASS_BITS]
- [cdcacm.h:TRACE_TRANSFER_BITS]
- [cdcacm.h:TRACE_CONTROLLER_BITS]
- [cdcacm.h:TRACE_INTERRUPT_BITS]
- [cdcacm.h:TRACE_BITSET]
- [sercon_main.c:main]
- [serdis_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_CDCACM]: Build and feature compilation gated by `CONFIG_SYSTEM_CDCACM`.
- [Kconfig:CONFIG_SYSTEM_CDCACM_DEVMINOR]: Build and feature compilation gated by `CONFIG_SYSTEM_CDCACM_DEVMINOR`.
- [Kconfig:depends on BOARDCTL && CDCACM]: Requires Kconfig dependency condition `BOARDCTL && CDCACM`.
- [Kconfig:depends on USBDEV_TRACE || DEBUG_USB]: Requires Kconfig dependency condition `USBDEV_TRACE || DEBUG_USB`.
- [cdcacm.h:CONFIG_USBDEV]: Conditional compilation gated by `CONFIG_USBDEV`.
- [cdcacm.h:CONFIG_CDCACM]: Conditional compilation gated by `CONFIG_CDCACM`.

## Side Effects
- [sercon_main.c:printf]: Writes formatted diagnostic, logging, or console output.
- [serdis_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
