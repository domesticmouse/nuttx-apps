# `benchmarks/sd_bench`

## Overview
Provides SD benchmark program (`benchmarks/sd_bench`). SD benchmark application based on https://github.com/PX4/PX4-Autopilot/blob/main/src/systemcmds/sd_bench/sd_bench.cpp

## Interface
- [Makefile:PROGNAME=$(CONFIG_BENCHMARK_SD_BENCH_PROGNAME)]
- [Kconfig:CONFIG_BENCHMARK_SD_BENCH]
- [Kconfig:CONFIG_BENCHMARK_SD_BENCH_PROGNAME]
- [Kconfig:CONFIG_BENCHMARK_SD_BENCH_PRIORITY]
- [Kconfig:CONFIG_BENCHMARK_SD_BENCH_STACKSIZE]
- [sd_bench_main.c:struct sdb_config]
- [sd_bench_main.c:sdb_config_t]
- [sd_bench_main.c:main]

## Invariants
- [Kconfig:CONFIG_BENCHMARK_SD_BENCH]: Build and feature compilation gated by `CONFIG_BENCHMARK_SD_BENCH`.
- [Kconfig:CONFIG_BENCHMARK_SD_BENCH_PROGNAME]: Build and feature compilation gated by `CONFIG_BENCHMARK_SD_BENCH_PROGNAME`.
- [Kconfig:depends on ALLOW_BSD_COMPONENTS]: Requires Kconfig dependency condition `ALLOW_BSD_COMPONENTS`.

## Side Effects
- [sd_bench_main.c:write]: Performs VFS file or device descriptor I/O operations.
- [sd_bench_main.c:malloc]: Allocates or releases dynamic heap memory.
- [sd_bench_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
