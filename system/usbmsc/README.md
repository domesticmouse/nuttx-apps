# `system/usbmsc`

## Overview
Provides USB Mass Storage Device Commands (`system/usbmsc`). Enable the USB mass storage class controls. These controls include:

## Interface
- [Makefile:PROGNAME=msconn]
- [Kconfig:CONFIG_SYSTEM_USBMSC]
- [Kconfig:CONFIG_SYSTEM_USBMSC_NLUNS]
- [Kconfig:CONFIG_SYSTEM_USBMSC_DEVMINOR1]
- [Kconfig:CONFIG_SYSTEM_USBMSC_DEVPATH1]
- [usbmsc.h:struct usbmsc_state_s]
- [usbmsc_main.c:struct usbmsc_lun_t]
- [usbmsc_main.c:main]
- [usbmsc_main.c:msdis_main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_USBMSC]: Build and feature compilation gated by `CONFIG_SYSTEM_USBMSC`.
- [Kconfig:CONFIG_SYSTEM_USBMSC_NLUNS]: Build and feature compilation gated by `CONFIG_SYSTEM_USBMSC_NLUNS`.
- [Kconfig:depends on BOARDCTL && USBMSC && BUILD_FLAT]: Requires Kconfig dependency condition `BOARDCTL && USBMSC && BUILD_FLAT`.
- [Kconfig:depends on USBDEV_TRACE || DEBUG_USB]: Requires Kconfig dependency condition `USBDEV_TRACE || DEBUG_USB`.
- [usbmsc.h:CONFIG_SYSTEM_USBMSC_DEBUGMM]: Conditional compilation gated by `CONFIG_SYSTEM_USBMSC_DEBUGMM`.
- [usbmsc_main.c:CONFIG_SYSTEM_USBMSC_TRACEINIT]: Conditional compilation gated by `CONFIG_SYSTEM_USBMSC_TRACEINIT`.

## Side Effects
- [usbmsc_main.c:bind]: Performs network socket creation, binding, or protocol I/O.
- [usbmsc_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
