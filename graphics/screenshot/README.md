# `graphics/screenshot`

## Overview
Provides TIFF screenshot utility (`graphics/screenshot`). Generate a NX screenshot utility based on the TIFF library.

## Interface
- [Makefile:PROGNAME=screenshot]
- [Kconfig:CONFIG_GRAPHICS_SCREENSHOT]
- [Kconfig:CONFIG_SCREENSHOT_WIDTH]
- [Kconfig:CONFIG_SCREENSHOT_HEIGHT]
- [Kconfig:CONFIG_SCREENSHOT_FORMAT]
- [screenshot_main.c:save_screenshot]
- [screenshot_main.c:main]

## Invariants
- [Kconfig:CONFIG_GRAPHICS_SCREENSHOT]: Build and feature compilation gated by `CONFIG_GRAPHICS_SCREENSHOT`.
- [Kconfig:CONFIG_SCREENSHOT_WIDTH]: Build and feature compilation gated by `CONFIG_SCREENSHOT_WIDTH`.
- [Kconfig:depends on TIFF && NX]: Requires Kconfig dependency condition `TIFF && NX`.
- [screenshot_main.c:CONFIG_SCREENSHOT_WIDTH]: Conditional compilation gated by `CONFIG_SCREENSHOT_WIDTH`.
- [screenshot_main.c:CONFIG_SCREENSHOT_HEIGHT]: Conditional compilation gated by `CONFIG_SCREENSHOT_HEIGHT`.
- [screenshot_main.c:CONFIG_SCREENSHOT_FORMAT]: Conditional compilation gated by `CONFIG_SCREENSHOT_FORMAT`.

## Side Effects
- [screenshot_main.c:malloc]: Allocates or releases dynamic heap memory.
- [screenshot_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
