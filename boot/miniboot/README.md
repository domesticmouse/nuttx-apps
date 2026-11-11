# Minimal NuttX Bootloader (`boot/miniboot`)

## Overview
Provides a minimal bootloader application (`miniboot`) that initializes the board and directly boots a firmware image at `CONFIG_MINIBOOT_SLOT_PATH` with header offset `CONFIG_MINIBOOT_HEADER_SIZE` via `boardctl(BOARDIOC_BOOT_IMAGE, ...)`.

## Interface
- `[miniboot_main.c:main]`: Entry point for the minimal bootloader application.

## Invariants
- None

## Side Effects
- `[miniboot_main.c:main]`: Logs a startup message via `syslog(LOG_INFO, ...)`, calls `boardctl(BOARDIOC_FINALINIT, 0)` when `CONFIG_BOARDCTL_FINALINIT` is defined, and invokes `boardctl(BOARDIOC_BOOT_IMAGE, (uintptr_t)&info)` with `CONFIG_MINIBOOT_SLOT_PATH` and `CONFIG_MINIBOOT_HEADER_SIZE`.

## Verification
- Run: `make test`
