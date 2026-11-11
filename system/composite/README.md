# `system/composite`

## Overview
Provides USB Composite Device Commands (`system/composite`). Enable the USB composite class controls. These controls include:

## Interface
- [Makefile:PROGNAME=conn]
- [Kconfig:CONFIG_SYSTEM_COMPOSITE]
- [Kconfig:CONFIG_SYSTEM_COMPOSITE_DEFCONFIG]
- [Kconfig:CONFIG_SYSTEM_COMPOSITE_TRACEINIT]
- [Kconfig:CONFIG_SYSTEM_COMPOSITE_TRACECLASS]
- [composite.h:struct composite_state_s]
- [composite.h:CONFIG_USBDEV_TRACE_INITIALIDSET]
- [composite.h:TRACE_INIT_BITS]
- [composite.h:TRACE_ERROR_BITS]
- [composite.h:TRACE_CLASS_BITS]
- [composite.h:TRACE_TRANSFER_BITS]
- [composite.h:TRACE_CONTROLLER_BITS]
- [composite.h:TRACE_INTERRUPT_BITS]
- [composite.h:TRACE_BITSET]
- [composite_main.c:main]
- [composite_main.c:disconn_main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_COMPOSITE]: Build and feature compilation gated by `CONFIG_SYSTEM_COMPOSITE`.
- [Kconfig:CONFIG_SYSTEM_COMPOSITE_DEFCONFIG]: Build and feature compilation gated by `CONFIG_SYSTEM_COMPOSITE_DEFCONFIG`.
- [Kconfig:depends on BOARDCTL && USBDEV_COMPOSITE && BUILD_FLAT]: Requires Kconfig dependency condition `BOARDCTL && USBDEV_COMPOSITE && BUILD_FLAT`.
- [composite.h:CONFIG_USBDEV]: Conditional compilation gated by `CONFIG_USBDEV`.
- [composite.h:CONFIG_USBDEV_COMPOSITE]: Conditional compilation gated by `CONFIG_USBDEV_COMPOSITE`.
- [composite.h:CONFIG_USBDEV_TRACE_INITIALIDSET]: Conditional compilation gated by `CONFIG_USBDEV_TRACE_INITIALIDSET`.

## Side Effects
- [composite_main.c:bind]: Performs network socket creation, binding, or protocol I/O.
- [composite_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
