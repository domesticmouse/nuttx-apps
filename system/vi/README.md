# `system/vi`

## Overview
Provides VI Work-Alike Text Editor (`system/vi`). Enable support for NuttX tiny VI work-alike editor.

## Interface
- [Makefile:PROGNAME=vi]
- [Kconfig:CONFIG_SYSTEM_VI]
- [Kconfig:CONFIG_SYSTEM_VI_COLS]
- [Kconfig:CONFIG_SYSTEM_VI_ROWS]
- [Kconfig:CONFIG_SYSTEM_VI_DEBUGLEVEL]
- [vi.c:enum vi_cmdmode_key_e]
- [vi.c:enum vi_insmode_key_e]
- [vi.c:enum vi_colonmode_key_e]
- [vi.c:enum vi_findmode_key_e]
- [vi.c:enum vi_mode_s]
- [vi.c:struct vi_pos_s]
- [vi.c:struct vi_undo_s]
- [vi.c:struct vi_s]
- [vi.c:vi_findnext]
- [vi.c:vi_findprev]
- [vi.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_VI]: Build and feature compilation gated by `CONFIG_SYSTEM_VI`.
- [Kconfig:CONFIG_SYSTEM_VI_COLS]: Build and feature compilation gated by `CONFIG_SYSTEM_VI_COLS`.
- [vi.c:CONFIG_SYSTEM_VI_ROWS]: Conditional compilation gated by `CONFIG_SYSTEM_VI_ROWS`.
- [vi.c:CONFIG_SYSTEM_VI_COLS]: Conditional compilation gated by `CONFIG_SYSTEM_VI_COLS`.
- [vi.c:CONFIG_SYSTEM_VI_YANK_THRESHOLD]: Conditional compilation gated by `CONFIG_SYSTEM_VI_YANK_THRESHOLD`.
- [vi.c:CONFIG_SYSTEM_VI_DEBUGLEVEL]: Conditional compilation gated by `CONFIG_SYSTEM_VI_DEBUGLEVEL`.

## Side Effects
- [vi.c:write]: Performs VFS file or device descriptor I/O operations.
- [vi.c:realloc]: Allocates or releases dynamic heap memory.
- [vi.c:syslog]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
