# `benchmarks/mtd`

## Overview
Provides MTD test and transfer rate benchmark (`benchmarks/mtd`). This testing/benchmark application performs an erase/write operation to evaluate write transfer rate and then reads the

## Interface
- [Makefile:PROGNAME=mtd]
- [Kconfig:CONFIG_BENCHMARK_MTD]
- [mtd.c:main]

## Invariants
- [Kconfig:CONFIG_BENCHMARK_MTD]: Build and feature compilation gated by `CONFIG_BENCHMARK_MTD`.
- [Kconfig:depends on BUILD_FLAT && MTD && LIBC_FLOATINGPOINT]: Requires Kconfig dependency condition `BUILD_FLAT && MTD && LIBC_FLOATINGPOINT`.

## Side Effects
- [mtd.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [mtd.c:write]: Performs VFS file or device descriptor I/O operations.
- [mtd.c:malloc]: Allocates or releases dynamic heap memory.
- [mtd.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
