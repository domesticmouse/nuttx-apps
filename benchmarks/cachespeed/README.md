# `benchmarks/cachespeed`

## Overview
Instruction and data cache latency/throughput benchmark (`cachespeed`) measuring cache invalidate, clean, and flush operations across varying buffer sizes.

## Interface
- [cachespeed_main.c:main]
- [Kconfig:BENCHMARK_CACHESPEED]
- [Kconfig:BENCHMARK_CACHESPEED_PROGNAME]
- [Kconfig:CACHESPEED_MONOTONIC_TIME]
- [Makefile:CACHESPEED_PERFTIME]

## Invariants
- [Kconfig:ARCH_ICACHE] and [Kconfig:ARCH_DCACHE]: Requires both instruction cache and data cache architecture support.
- [cachespeed_main.c:setup]: Allocated buffer address `cs->addr` must be non-zero or the process terminates with `EXIT_FAILURE`.
- [cachespeed_main.c:REPEAT_NUM]: Repeat count per cache size step is fixed at `1000` iterations.

## Side Effects
- [cachespeed_main.c:setup] and [cachespeed_main.c:teardown]: Allocate half of total free heap memory (`info.fordblks / 2`) via `malloc` and release it via `free`.
- [cachespeed_main.c:test_skeleton] and [cachespeed_main.c:cachespeed_common]: Enter critical sections (disabling interrupts) and execute `up_invalidate_dcache`, `up_clean_dcache`, `up_flush_dcache`, and `up_invalidate_icache`.
- [cachespeed_main.c:report_line]: Writes benchmark progress and throughput metrics to `stdout`.

## Verification
- Run: `make test`
