# `system/resmonitor`

## Overview
Provides enable resource monitor [showinfo] (`system/resmonitor`). Enable resource show with specific duration. Should not use with LOW_RESOURCE_TEST at the same time.

## Interface
- [Makefile:PROGNAME=showinfo]
- [Makefile:PROGNAME=filldisk]
- [Makefile:PROGNAME=fillcpu]
- [Makefile:PROGNAME=fillmem]
- [Kconfig:CONFIG_SYSTEM_RESMONITOR]
- [Kconfig:CONFIG_SYSTEM_RESMONITOR_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_RESMONITOR_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_RESMONITOR_FILL]
- [fillcpu.c:main]
- [filldisk.c:main]
- [fillmem.c:main]
- [showinfo.c:struct t_info]
- [showinfo.c:struct p_info]
- [showinfo.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_RESMONITOR]: Build and feature compilation gated by `CONFIG_SYSTEM_RESMONITOR`.
- [Kconfig:CONFIG_SYSTEM_RESMONITOR_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_RESMONITOR_PRIORITY`.

## Side Effects
- [fillcpu.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [fillcpu.c:syslog]: Writes formatted diagnostic, logging, or console output.
- [filldisk.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [filldisk.c:malloc]: Allocates or releases dynamic heap memory.
- [filldisk.c:syslog]: Writes formatted diagnostic, logging, or console output.
- [fillmem.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
