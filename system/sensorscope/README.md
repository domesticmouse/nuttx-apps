# `system/sensorscope`

## Overview
Provides NxScope sensors stream app (`system/sensorscope`). Ignored if set to 0 (for example for RTT interface)

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_SENSORSCOPE_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_SENSORSCOPE]
- [Kconfig:CONFIG_SYSTEM_SENSORSCOPE_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_SENSORSCOPE_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_SENSORSCOPE_STACKSIZE]
- [sensorscope_main.c:struct nxsensor_info_s]
- [sensorscope_main.c:struct listen_object_s]
- [sensorscope_main.c:struct nxscope_thr_env_s]
- [sensorscope_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_SENSORSCOPE]: Build and feature compilation gated by `CONFIG_SYSTEM_SENSORSCOPE`.
- [Kconfig:CONFIG_SYSTEM_SENSORSCOPE_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_SENSORSCOPE_PROGNAME`.
- [Kconfig:depends on LOGGING_NXSCOPE]: Requires Kconfig dependency condition `LOGGING_NXSCOPE`.
- [Kconfig:depends on CDCACM]: Requires Kconfig dependency condition `CDCACM`.
- [sensorscope_main.c:DEBUGASSERT]: Enforces `DEBUGASSERT(envp)` precondition.
- [sensorscope_main.c:CONFIG_SENSORS_USE_B16]: Conditional compilation gated by `CONFIG_SENSORS_USE_B16`.

## Side Effects
- [sensorscope_main.c:read]: Performs VFS file or device descriptor I/O operations.
- [sensorscope_main.c:malloc]: Allocates or releases dynamic heap memory.
- [sensorscope_main.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [sensorscope_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
