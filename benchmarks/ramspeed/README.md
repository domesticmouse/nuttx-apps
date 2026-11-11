# `benchmarks/ramspeed`

## Overview
RAM `memcpy` and `memset` throughput benchmark (`ramspeed`) across power-of-two block sizes from 32 bytes up to a user-specified buffer size.

## Interface
- [ramspeed_main.c:main]
- [Kconfig:BENCHMARK_RAMSPEED]
- [Kconfig:BENCHMARK_RAMSPEED_PROGNAME]
- [Kconfig:BENCHMARK_RAMSPEED_PRIORITY]
- [Kconfig:BENCHMARK_RAMSPEED_STACKSIZE]

## Invariants
- [Kconfig:BENCHMARK_RAMSPEED]: Depends on `LIBC_FLOATINGPOINT`.
- [ramspeed_main.c:parse_commandline]: Requires `argc >= 4`, addresses aligned to `ALIGN_MASK`, `size >= 32`, `repeat_num > 0`, and either `-a` or `-w`.
- [ramspeed_main.c:HAS_IRQ_CONTROL]: Interrupt-disable mode (`-i`) is only available when neither `CONFIG_BUILD_KERNEL` nor `CONFIG_BUILD_PROTECTED` is defined.

## Side Effects
- [ramspeed_main.c:main]: Allocates and frees heap buffers via `malloc`/`free` when `-a` is passed.
- [ramspeed_main.c:memcpy_speed_test] and [ramspeed_main.c:memset_speed_test]: Overwrite destination memory buffers, optionally disable interrupts via `enter_critical_section`, and print KB/s rates to `stdout`.

## Verification
- Run: `make test`
