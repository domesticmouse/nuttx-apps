# `system/critmon`

## Overview
Provides Critcal Section Monitor (`system/critmon`). If the critical section monitor is enabled (CONFIGSCHED_CRITMONITOR) this option will enable a critical section monitor daemon. This daemon

## Interface
- [Makefile:PROGNAME=critmon]
- [Kconfig:CONFIG_SYSTEM_CRITMONITOR]
- [Kconfig:CONFIG_SYSTEM_CRITMONITOR_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_CRITMONITOR_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_CRITMONITOR_DAEMON_STACKSIZE]
- [critmon.c:struct critmon_state_s]
- [critmon.c:critmon_start_main]
- [critmon.c:critmon_stop_main]
- [critmon.c:critmon_main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_CRITMONITOR]: Build and feature compilation gated by `CONFIG_SYSTEM_CRITMONITOR`.
- [Kconfig:CONFIG_SYSTEM_CRITMONITOR_STACKSIZE]: Build and feature compilation gated by `CONFIG_SYSTEM_CRITMONITOR_STACKSIZE`.
- [Kconfig:depends on FS_PROCFS && !FS_PROCFS_EXCLUDE_PROCESS && SCHED_CRITMONITOR]: Requires Kconfig dependency condition `FS_PROCFS && !FS_PROCFS_EXCLUDE_PROCESS && SCHED_CRITMONITOR`.
- [critmon.c:sched_lock]: Synchronizes concurrent access across threads or critical sections.
- [critmon.c:CONFIG_SYSTEM_CRITMONITOR]: Conditional compilation gated by `CONFIG_SYSTEM_CRITMONITOR`.
- [critmon.c:CONFIG_SYSTEM_CRITMONITOR_DAEMON_STACKSIZE]: Conditional compilation gated by `CONFIG_SYSTEM_CRITMONITOR_DAEMON_STACKSIZE`.

## Side Effects
- [critmon.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [critmon.c:free]: Allocates or releases dynamic heap memory.
- [critmon.c:task_create]: Spawns child tasks, pthreads, or built-in applications.
- [critmon.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
