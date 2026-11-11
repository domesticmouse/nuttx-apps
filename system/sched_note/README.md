# `system/sched_note`

## Overview
Provides Scheduler monitor (`system/sched_note`). Enable the schedler instrumentation monitor

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_NOTE_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_NOTE]
- [Kconfig:CONFIG_SYSTEM_NOTE_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_NOTE_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_NOTE_STACKSIZE]
- [note_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NOTE]: Build and feature compilation gated by `CONFIG_SYSTEM_NOTE`.
- [Kconfig:CONFIG_SYSTEM_NOTE_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_NOTE_PROGNAME`.
- [Kconfig:depends on DRIVERS_NOTERAM]: Requires Kconfig dependency condition `DRIVERS_NOTERAM`.

## Side Effects
- [note_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [note_main.c:task_create]: Spawns child tasks, pthreads, or built-in applications.
- [note_main.c:syslog]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
