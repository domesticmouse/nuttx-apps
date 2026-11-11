# `benchmarks/spinlock_bench`

## Overview
Multi-threaded spinlock contention benchmark (`spinlock_bench`) measuring lock acquisition/release throughput across concurrent pthreads.

## Interface
- [spinlock_bench.c:main]
- [Kconfig:BENCHMARK_SPINLOCK]
- [Kconfig:SPINLOCK_PROGNAME]
- [Kconfig:SPINLOCK_MULTITHREAD]
- [Kconfig:SPINLOCK_ITERATIONS]

## Invariants
- [Kconfig:BENCHMARK_SPINLOCK]: Depends on `BUILD_FLAT`.
- [spinlock_bench.c:main]: Asserts `pthread_create` returns `0` and verifies that the final shared counter equals `THREAD_NUM * TEST_NUM` after all threads join.

## Side Effects
- [spinlock_bench.c:thread_spinlock] and [spinlock_bench.c:main]: Spawn `THREAD_NUM` pthreads acquiring/releasing a shared spinlock (`spin_lock`/`spin_unlock`), increment a shared counter, and print elapsed `perf_gettime()` ticks to `stdout`.

## Verification
- Run: `make test`
