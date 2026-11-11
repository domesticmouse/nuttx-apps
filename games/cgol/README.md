# `games/cgol`

## Overview
Provides Conway's Game of Life (`games/cgol`). Enable Conway's Game of Life.

## Interface
- [Makefile:PROGNAME=$(CONFIG_GAMES_CGOL_PROGNAME)]
- [Kconfig:CONFIG_GAMES_CGOL]
- [Kconfig:CONFIG_GAMES_CGOL_PROGNAME]
- [Kconfig:CONFIG_GAMES_CGOL_PRIORITY]
- [Kconfig:CONFIG_GAMES_CGOL_STACKSIZE]
- [cgol_main.c:struct fb_state_s]
- [cgol_main.c:main]

## Invariants
- [Kconfig:CONFIG_GAMES_CGOL]: Build and feature compilation gated by `CONFIG_GAMES_CGOL`.
- [Kconfig:CONFIG_GAMES_CGOL_PROGNAME]: Build and feature compilation gated by `CONFIG_GAMES_CGOL_PROGNAME`.
- [Kconfig:depends on VIDEO_FB]: Requires Kconfig dependency condition `VIDEO_FB`.
- [cgol_main.c:DEBUGASSERT]: Enforces `DEBUGASSERT(count <= 8)` precondition.
- [cgol_main.c:DEBUGASSERT]: Enforces `DEBUGASSERT(render_cell != NULL)` precondition.
- [cgol_main.c:DEBUGASSERT]: Enforces `DEBUGASSERT(bit_index > 0)` precondition.

## Side Effects
- [cgol_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [cgol_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [cgol_main.c:malloc]: Allocates or releases dynamic heap memory.
- [cgol_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
