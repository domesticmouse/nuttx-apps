# `benchmarks`

## Overview
Groups Benchmark Applications (`benchmarks`) components and utilities for NuttX.

## Subdirectories & Boundaries
- `cachespeed`: [./cachespeed/README.md](./cachespeed/README.md) - Instruction and data cache latency/throughput benchmark (`cachespeed`) measuring cache invalidate, clean, and flush operations across varying buffer sizes.
- `cyclictest`: [./cyclictest/README.md](./cyclictest/README.md) - Provides Cyclictest (`benchmarks/cyclictest`). Enable the cyclictest application.
- `mtd`: [./mtd/README.md](./mtd/README.md) - Provides MTD test and transfer rate benchmark (`benchmarks/mtd`). This testing/benchmark application performs an erase/write operation to evaluate write transfer rate and then reads the
- `osperf`: [./osperf/README.md](./osperf/README.md) - Real-time operating system micro-benchmark (`osperf`) measuring latency of pthread creation, context switching, high-priority work queues, pipes, `poll()`, and POSIX semaphores.
- `ramspeed`: [./ramspeed/README.md](./ramspeed/README.md) - RAM `memcpy` and `memset` throughput benchmark (`ramspeed`) across power-of-two block sizes from 32 bytes up to a user-specified buffer size.
- `rt-tests`: [./rt-tests/README.md](./rt-tests/README.md) - Provides RT-Tests (`benchmarks/rt-tests`). Measure the timer jitter
- `sd_bench`: [./sd_bench/README.md](./sd_bench/README.md) - Provides SD benchmark program (`benchmarks/sd_bench`). SD benchmark application based on https://github.com/PX4/PX4-Autopilot/blob/main/src/systemcmds/sd_bench/sd_bench.cpp
- `spinlock_bench`: [./spinlock_bench/README.md](./spinlock_bench/README.md) - Multi-threaded spinlock contention benchmark (`spinlock_bench`) measuring lock acquisition/release throughput across concurrent pthreads.
- `tacle-bench`: [./tacle-bench/README.md](./tacle-bench/README.md) - Provides TacleBench (`benchmarks/tacle-bench`). A real-time benchmark from WCET'16.
- `whetstone`: [./whetstone/README.md](./whetstone/README.md) - Provides Double Precision Benchmark (`benchmarks/whetstone`). Enable a Whetstone test.
