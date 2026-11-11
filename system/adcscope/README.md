# `system/adcscope`

## Overview
Provides NxScope ADC stream app (`system/adcscope`). Ignored if set to 0 (for example for RTT interface)

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_ADCSCOPE_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_ADCSCOPE]
- [Kconfig:CONFIG_SYSTEM_ADCSCOPE_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_ADCSCOPE_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_ADCSCOPE_STACKSIZE]
- [adcscope_main.c:struct adcscope_thr_env_s]
- [adcscope_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_ADCSCOPE]: Build and feature compilation gated by `CONFIG_SYSTEM_ADCSCOPE`.
- [Kconfig:CONFIG_SYSTEM_ADCSCOPE_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_ADCSCOPE_PROGNAME`.
- [Kconfig:depends on ADC && LOGGING_NXSCOPE]: Requires Kconfig dependency condition `ADC && LOGGING_NXSCOPE`.
- [Kconfig:depends on CDCACM]: Requires Kconfig dependency condition `CDCACM`.
- [adcscope_main.c:DEBUGASSERT]: Enforces `DEBUGASSERT(envp)` precondition.
- [adcscope_main.c:CONFIG_SYSTEM_ADCSCOPE_INT16]: Conditional compilation gated by `CONFIG_SYSTEM_ADCSCOPE_INT16`.

## Side Effects
- [adcscope_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [adcscope_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [adcscope_main.c:zalloc]: Allocates or releases dynamic heap memory.
- [adcscope_main.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [adcscope_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
