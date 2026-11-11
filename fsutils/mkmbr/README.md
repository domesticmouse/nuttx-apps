# Master Boot Record Formatter (`fsutils/mkmbr`)

## Overview
Implements the `mkmbr` command-line utility (`CONFIG_FSUTILS_MKMBR`) for writing a 512-byte Master Boot Record (MBR) with up to four primary partitions onto a block device.

## Interface
- `[mkmbr.c:main]`: CLI entry point (`mkmbr`) parsing device path and `(start, size)` partition pairs.
- `[Kconfig:FSUTILS_MKMBR]`, `[Makefile:PROGNAME]`: Build configuration and application target (`mkmbr`).

## Invariants
- `[mkmbr.c:main]`: Requires `argc >= 4`, `argc % 2 == 0`, and partition count `(argc - 2) / 2 <= 4`.
- `[mkmbr.c:main]`: Each partition's `start` sector must be `>=` the next free sector (initially `1`), and `start + size` must not exceed total 512-byte device sectors (`bsize`).

## Side Effects
- `[mkmbr.c:main]`: Opens the target block device `O_RDWR`, queries its size via `fstat`, writes a 512-byte MBR sector (partition type `0x83`, boot signature `0xAA55`) to sector 0, and closes the descriptor.
- `[mkmbr.c:print_usage]`: Writes usage diagnostics to `STDERR_FILENO` on invalid arguments.

## Verification
- Run: `make test`
