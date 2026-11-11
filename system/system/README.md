# `system/system`

## Overview
Provides System Command (`system/system`). Enable support for the system() interface. This will support execution of NSH commands from C code.

## Interface
- [Kconfig:CONFIG_SYSTEM_SYSTEM]
- [Kconfig:CONFIG_SYSTEM_SYSTEM_SHPATH]
- [Kconfig:CONFIG_SYSTEM_SYSTEM_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_SYSTEM_PRIORITY]
- [system.c:system]

## Invariants
- [Kconfig:CONFIG_SYSTEM_SYSTEM]: Build and feature compilation gated by `CONFIG_SYSTEM_SYSTEM`.
- [Kconfig:CONFIG_SYSTEM_SYSTEM_SHPATH]: Build and feature compilation gated by `CONFIG_SYSTEM_SYSTEM_SHPATH`.
- [Kconfig:depends on NSH_LIBRARY]: Requires Kconfig dependency condition `NSH_LIBRARY`.
- [Kconfig:depends on SYSTEM_NSH=m]: Requires Kconfig dependency condition `SYSTEM_NSH=m`.
- [system.c:DEBUGASSERT]: Enforces `DEBUGASSERT(cmd != NULL)` precondition.
- [system.c:CONFIG_SYSTEM_SYSTEM_DUMPINFO]: Conditional compilation gated by `CONFIG_SYSTEM_SYSTEM_DUMPINFO`.

## Side Effects
- [system.c:posix_spawn]: Spawns child tasks, pthreads, or built-in applications.
- [system.c:syslog]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
