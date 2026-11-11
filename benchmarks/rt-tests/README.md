# `benchmarks/rt-tests`

## Overview
Provides RT-Tests (`benchmarks/rt-tests`). Measure the timer jitter

## Interface
- [Makefile:PROGNAME=cyclictest]
- [Kconfig:CONFIG_BENCHMARK_RTTESTS]
- [Kconfig:CONFIG_BENCHMARK_RTTESTS_PRIORITY]
- [Kconfig:CONFIG_BENCHMARK_RTTESTS_STACKSIZE]
- [numa.h:struct bitmask]
- [numa.h:numa_allocate_cpumask]
- [numa.h:numa_bitmask_free]
- [numa.h:numa_sched_getaffinity]
- [numa.h:numa_bitmask_isbitset]
- [numa.h:numa_bitmask_clearbit]
- [numa.h:numa_parse_cpustring_all]
- [numa.h:numa_bitmask_weight]
- [numa.h:CACHE_LINESIZE]

## Invariants
- [Kconfig:CONFIG_BENCHMARK_RTTESTS]: Build and feature compilation gated by `CONFIG_BENCHMARK_RTTESTS`.
- [Kconfig:CONFIG_BENCHMARK_RTTESTS_PRIORITY]: Build and feature compilation gated by `CONFIG_BENCHMARK_RTTESTS_PRIORITY`.
- [Kconfig:depends on PIPES && ALLOW_GPL_COMPONENTS]: Requires Kconfig dependency condition `PIPES && ALLOW_GPL_COMPONENTS`.

## Side Effects
- [numa.h:free]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
