# `benchmarks/cyclictest`

## Overview
Provides Cyclictest (`benchmarks/cyclictest`). Enable the cyclictest application.

## Interface
- [Makefile:PROGNAME=$(CONFIG_BENCHMARK_CYCLICTEST_PROGNAME)]
- [Kconfig:CONFIG_BENCHMARK_CYCLICTEST]
- [Kconfig:CONFIG_BENCHMARK_CYCLICTEST_PROGNAME]
- [Kconfig:CONFIG_BENCHMARK_CYCLICTEST_PRIORITY]
- [Kconfig:CONFIG_BENCHMARK_CYCLICTEST_STACKSIZE]
- [cyclictest.c:enum meas_method_e]
- [cyclictest.c:enum wait_method_e]
- [cyclictest.c:struct cyclictest_config_s]
- [cyclictest.c:struct thread_param_s]
- [cyclictest.c:struct thread_stats_s]
- [cyclictest.c:main]

## Invariants
- [Kconfig:CONFIG_BENCHMARK_CYCLICTEST]: Build and feature compilation gated by `CONFIG_BENCHMARK_CYCLICTEST`.
- [Kconfig:CONFIG_BENCHMARK_CYCLICTEST_PROGNAME]: Build and feature compilation gated by `CONFIG_BENCHMARK_CYCLICTEST_PROGNAME`.

## Side Effects
- [cyclictest.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [cyclictest.c:open]: Performs VFS file or device descriptor I/O operations.
- [cyclictest.c:calloc]: Allocates or releases dynamic heap memory.
- [cyclictest.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [cyclictest.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
