# `benchmarks/tacle-bench`

## Overview
Provides TacleBench (`benchmarks/tacle-bench`). A real-time benchmark from WCET'16.

## Interface
- [Makefile:PROGNAME=taclebench]
- [Kconfig:CONFIG_BENCHMARK_TACLEBENCH]
- [Kconfig:CONFIG_BENCHMARK_TACLEBENCH_PRIORITY]
- [Kconfig:CONFIG_BENCHMARK_TACLEBENCH_STACKSIZE]
- [generate_taclebench_c.sh]
- [generate_taclebench_c.sh:search_main]
- [generate_taclebench_c.sh:find_c_files]

## Invariants
- [Kconfig:CONFIG_BENCHMARK_TACLEBENCH]: Build and feature compilation gated by `CONFIG_BENCHMARK_TACLEBENCH`.
- [Kconfig:CONFIG_BENCHMARK_TACLEBENCH_PRIORITY]: Build and feature compilation gated by `CONFIG_BENCHMARK_TACLEBENCH_PRIORITY`.

## Side Effects
- [generate_taclebench_c.sh]: Executes shell utilities and generates or modifies build artifacts.

## Verification
- Run: `make test`
