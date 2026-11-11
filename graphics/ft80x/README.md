# `graphics/ft80x`

## Overview
Provides FTDI/BridgeTek FT80x library (`graphics/ft80x`). Enable support for the FTDI/BridgeTek FT80x library.

## Interface
- [Kconfig:CONFIG_GRAPHICS_FT80X]
- [Kconfig:CONFIG_GRAPHICS_FT80X_BUFSIZE]
- [Kconfig:CONFIG_GRAPHICS_FT80X_CMDEMPTY_SIGNAL]
- [Kconfig:CONFIG_GRAPHICS_FT80X_TAG_SIGNAL]
- [ft80x.h:ft80x_getreg8]
- [ft80x.h:ft80x_getreg16]
- [ft80x.h:ft80x_getreg32]
- [ft80x.h:ft80x_getregs]
- [ft80x.h:ft80x_putreg8]
- [ft80x.h:ft80x_putreg16]
- [ft80x.h:ft80x_putreg32]
- [ft80x.h:ft80x_putregs]
- [ft80x.h:ft80x_ramdl_rewind]
- [ft80x.h:ft80x_ramdl_append]
- [ft80x.h:ft80x_ramcmd_append]
- [ft80x.h:ft80x_ramcmd_freespace]
- [ft80x.h:ft80x_ramcmd_waitfifoempty]
- [ft80x.h:ft80x_dl_swap]

## Invariants
- [Kconfig:CONFIG_GRAPHICS_FT80X]: Build and feature compilation gated by `CONFIG_GRAPHICS_FT80X`.
- [Kconfig:CONFIG_GRAPHICS_FT80X_BUFSIZE]: Build and feature compilation gated by `CONFIG_GRAPHICS_FT80X_BUFSIZE`.
- [Kconfig:depends on GRAPHICS_FT80X_DEBUG_ERROR]: Requires Kconfig dependency condition `GRAPHICS_FT80X_DEBUG_ERROR`.
- [Kconfig:depends on GRAPHICS_FT80X_DEBUG_WARN]: Requires Kconfig dependency condition `GRAPHICS_FT80X_DEBUG_WARN`.
- [ft80x.h:CONFIG_GRAPHICS_FT80X]: Conditional compilation gated by `CONFIG_GRAPHICS_FT80X`.
- [ft80x.h:CONFIG_GRAPHICS_FT80X_DEBUG_ERROR]: Conditional compilation gated by `CONFIG_GRAPHICS_FT80X_DEBUG_ERROR`.

## Side Effects
- [ft80x.h:fprintf]: Writes formatted diagnostic, logging, or console output.
- [ft80x_audio.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [ft80x_audio.c:open]: Performs VFS file or device descriptor I/O operations.
- [ft80x_backlight.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [ft80x_dl.c:printf]: Writes formatted diagnostic, logging, or console output.
- [ft80x_ramcmd.c:ioctl]: Issues device/driver control requests via `ioctl()`.

## Verification
- Run: `make test`
