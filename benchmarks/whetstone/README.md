# `benchmarks/whetstone`

## Overview
Provides Double Precision Benchmark (`benchmarks/whetstone`). Enable a Whetstone test.

## Interface
- [Makefile:PROGNAME=$(CONFIG_BENCHMARK_WHETSTONE_PROGNAME)]
- [Kconfig:CONFIG_BENCHMARK_WHETSTONE]
- [Kconfig:CONFIG_BENCHMARK_WHETSTONE_PROGNAME]
- [Kconfig:CONFIG_BENCHMARK_WHETSTONE_PRIORITY]
- [Kconfig:CONFIG_BENCHMARK_WHETSTONE_STACKSIZE]
- [whetstone.c:pout]
- [whetstone.c:pa]
- [whetstone.c:p0]
- [whetstone.c:p3]
- [whetstone.c:main]

## Invariants
- [Kconfig:CONFIG_BENCHMARK_WHETSTONE]: Build and feature compilation gated by `CONFIG_BENCHMARK_WHETSTONE`.
- [Kconfig:CONFIG_BENCHMARK_WHETSTONE_PROGNAME]: Build and feature compilation gated by `CONFIG_BENCHMARK_WHETSTONE_PROGNAME`.
- [Kconfig:depends on ALLOW_CUSTOM_PERMISSIVE_COMPONENTS]: Requires Kconfig dependency condition `ALLOW_CUSTOM_PERMISSIVE_COMPONENTS`.

## Side Effects
- [whetstone.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
