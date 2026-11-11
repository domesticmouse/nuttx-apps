# `graphics/jpgresizetool`

## Overview
Provides JPGResizeTool (`graphics/jpgresizetool`). Libjpeg JPEG resizer

## Interface
- [Makefile:PROGNAME=jpgresize]
- [Kconfig:CONFIG_GRAPHICS_JPGRESIZETOOL]
- [resize.c:main]

## Invariants
- [Kconfig:CONFIG_GRAPHICS_JPGRESIZETOOL]: Build and feature compilation gated by `CONFIG_GRAPHICS_JPGRESIZETOOL`.
- [Kconfig:depends on libjpeg]: Requires Kconfig dependency condition `libjpeg`.

## Side Effects
- [resize.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [resize.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
