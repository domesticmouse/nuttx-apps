# `system/termcurses`

## Overview
Provides Terminal Curses control support (`system/termcurses`). Terminal emulation library for curses support on TTY type consoles such as serial port, CDCACM, telnet, etc.

## Interface
- [Kconfig:CONFIG_SYSTEM_TERMCURSES]
- [Kconfig:CONFIG_SYSTEM_TERMCURSES_VT100]
- [Kconfig:CONFIG_SYSTEM_TERMCURSES_VT100_OSX_ALT_CODES]
- [Kconfig:CONFIG_SYSTEM_TERMCURSES_DEBUG_KEYCODES]
- [tcurses_vt100.c:struct tcurses_vt100_s]
- [tcurses_vt100.c:struct keycodes_s]
- [tcurses_vt100.c:tcurses_vt100_initialize]
- [termcurses.c:termcurses_initterm]
- [termcurses.c:termcurses_deinitterm]
- [termcurses.c:termcurses_moveyx]
- [termcurses.c:termcurses_setcolors]
- [termcurses.c:termcurses_setattribute]
- [termcurses.c:termcurses_getwinsize]
- [termcurses.c:termcurses_getkeycode]
- [termcurses.c:termcurses_checkkey]

## Invariants
- [Kconfig:CONFIG_SYSTEM_TERMCURSES]: Build and feature compilation gated by `CONFIG_SYSTEM_TERMCURSES`.
- [Kconfig:CONFIG_SYSTEM_TERMCURSES_VT100]: Build and feature compilation gated by `CONFIG_SYSTEM_TERMCURSES_VT100`.
- [Kconfig:depends on SYSTEM_TERMCURSES]: Requires Kconfig dependency condition `SYSTEM_TERMCURSES`.
- [Kconfig:depends on SYSTEM_TERMCURSES_VT100]: Requires Kconfig dependency condition `SYSTEM_TERMCURSES_VT100`.
- [tcurses_vt100.c:CONFIG_TERMINFO_INCLUDE_NAME]: Conditional compilation gated by `CONFIG_TERMINFO_INCLUDE_NAME`.
- [tcurses_vt100.c:CONFIG_TERMCURSES_INCLUDE_TERMINFO_NAME]: Conditional compilation gated by `CONFIG_TERMCURSES_INCLUDE_TERMINFO_NAME`.

## Side Effects
- [tcurses_vt100.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [tcurses_vt100.c:write]: Performs VFS file or device descriptor I/O operations.
- [tcurses_vt100.c:zalloc]: Allocates or releases dynamic heap memory.
- [tcurses_vt100.c:printf]: Writes formatted diagnostic, logging, or console output.
- [termcurses.c:free]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
