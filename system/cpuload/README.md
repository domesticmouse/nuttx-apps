# `system/cpuload`

## Overview
Implements cpuload test (`system/cpuload`) for the NuttX application subsystem.

## Interface
- [Makefile:PROGNAME=cpuload]
- [Kconfig:CONFIG_SYSTEM_CPULOAD]
- [cpuload_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_CPULOAD]: Build and feature compilation gated by `CONFIG_SYSTEM_CPULOAD`.
- [cpuload_main.c:CONFIG_SCHED_CPULOAD_EXTCLK]: Conditional compilation gated by `CONFIG_SCHED_CPULOAD_EXTCLK`.
- [cpuload_main.c:CONFIG_SMP]: Conditional compilation gated by `CONFIG_SMP`.

## Side Effects
- [cpuload_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
