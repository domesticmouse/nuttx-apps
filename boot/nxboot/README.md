# NuttX Bootloader (`boot/nxboot`)

## Overview
Implements the standalone NuttX Bootloader (`nxboot`) application entry point and library, providing A/B/recovery MTD flash partition management, CRC32 image verification, automatic rollback/revert, and image boot handoff via `boardctl(BOARDIOC_BOOT_IMAGE, ...)`.

## Interface
- `[nxboot_main.c:main]`: Bootloader application entry point that checks reset cause, triggers slot validation/updates via `nxboot_perform_update()`, optionally copies the image to RAM via `nxboot_ramcopy()`, and boots the primary slot image.
- `[nxboot_main.c:nxboot_progress]`: Progress reporting callback printing status messages and percentage completion to `STDOUT_FILENO`.
- Subdirectories:
  - `include`: [./include/README.md](./include/README.md) - Public `nxboot.h` API declarations, image header structures, and slot constants.
  - `loader`: [./loader/README.md](./loader/README.md) - Flash partition access, CRC32 validation, and slot update/revert implementation.
  - `tools`: [./tools/README.md](./tools/README.md) - Host Python script (`nximage.py`) for prepending `nxboot` headers to firmware binaries.

## Invariants
- `[nxboot_main.c:nxboot_progress]`: Requires `g_progress_started` to be true before `nxboot_progress_dot`, `nxboot_progress_percent`, or `nxboot_progress_end` is invoked, and asserts non-NULL message strings in `progress_msgs`.
- `[nxboot_main.c:main]`: When `CONFIG_NXBOOT_SWRESET_ONLY` is enabled, full update/revert (`check_only = false`) is performed only if the reset cause is `BOARDIOC_RESETCAUSE_CPU_SOFT`, `BOARDIOC_RESETCAUSE_CPU_RWDT`, or `BOARDIOC_RESETCAUSE_PIN`; otherwise `check_only` remains `true`.

## Side Effects
- `[nxboot_main.c:nxboot_progress]` and `[nxboot_main.c:main]`: Write progress output to `STDOUT_FILENO` via `dprintf`, log status and errors via `syslog`, and mutate file-scope progress state (`g_progress_started`, `g_progress_percent_started`).
- `[nxboot_main.c:main]`: Invokes `boardctl` with `BOARDIOC_FINALINIT`, `BOARDIOC_RESET_CAUSE`, and `BOARDIOC_BOOT_IMAGE`, calls `nxboot_perform_update()`, and optionally copies the boot image to RAM via `nxboot_ramcopy()`.

## Verification
- Run: `make test`
