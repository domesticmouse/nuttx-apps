# `system/stackmonitor`

## Overview
Provides Stack Monitor (`system/stackmonitor`). If the stack coloration feature is enabled (STACK_COLORATION) this option will select the Stack Monitor. The stack monitor is a daemon

## Interface
- [Makefile:PROGNAME=stackmonitor_start]
- [Kconfig:CONFIG_SYSTEM_STACKMONITOR]
- [Kconfig:CONFIG_SYSTEM_STACKMONITOR_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_STACKMONITOR_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_STACKMONITOR_INTERVAL]
- [stackmonitor.c:struct stkmon_state_s]
- [stackmonitor.c:main]
- [stackmonitor.c:stackmonitor_stop_main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_STACKMONITOR]: Build and feature compilation gated by `CONFIG_SYSTEM_STACKMONITOR`.
- [Kconfig:CONFIG_SYSTEM_STACKMONITOR_STACKSIZE]: Build and feature compilation gated by `CONFIG_SYSTEM_STACKMONITOR_STACKSIZE`.
- [Kconfig:depends on FS_PROCFS && !FS_PROCFS_EXCLUDE_PROCESS && STACK_COLORATION]: Requires Kconfig dependency condition `FS_PROCFS && !FS_PROCFS_EXCLUDE_PROCESS && STACK_COLORATION`.
- [stackmonitor.c:sched_lock]: Synchronizes concurrent access across threads or critical sections.
- [stackmonitor.c:CONFIG_SYSTEM_STACKMONITOR]: Conditional compilation gated by `CONFIG_SYSTEM_STACKMONITOR`.
- [stackmonitor.c:CONFIG_SYSTEM_STACKMONITOR_STACKSIZE]: Conditional compilation gated by `CONFIG_SYSTEM_STACKMONITOR_STACKSIZE`.

## Side Effects
- [stackmonitor.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [stackmonitor.c:free]: Allocates or releases dynamic heap memory.
- [stackmonitor.c:task_create]: Spawns child tasks, pthreads, or built-in applications.
- [stackmonitor.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
