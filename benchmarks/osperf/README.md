# `benchmarks/osperf`

## Overview
Real-time operating system micro-benchmark (`osperf`) measuring latency of pthread creation, context switching, high-priority work queues, pipes, `poll()`, and POSIX semaphores.

## Interface
- [osperf.c:main]
- [osperf.c:performance_list]
- [Kconfig:BENCHMARK_OSPERF]
- [Kconfig:BENCHMARK_OSPERF_PRIORITY]
- [Kconfig:BENCHMARK_OSPERF_STACKSIZE]

## Invariants
- [Kconfig:BENCHMARK_OSPERF]: Depends on `PIPES` and `SCHED_HPWORK`.
- [osperf.c:performance_thread_create]: Asserts `tid > 0` after `pthread_create`.
- [osperf.c:hpwork_performance] and [osperf.c:pipe_performance]: Assert `work_queue(HPWORK, ...)` and `pipe(pipefd)` return `0`.

## Side Effects
- [osperf.c:performance_run]: Enters critical sections around benchmark executions and prints timing statistics (Max/Min/Avg ns) to `stdout`.
- [osperf.c:performance_thread_create]: Spawns and joins `SCHED_FIFO` pthreads, queues `HPWORK` items, creates/polls pipes, and operates on POSIX semaphores.

## Verification
- Run: `make test`
