# Graphics / `pdcurs34` PDCurses

## Overview

**Welcome to PDCurses!**

Public Domain Curses, aka PDCurses, is an implementation of X/Open curses for
multiple platforms. The latest version can be found at:

[pdcurses.sourceforge.net](http://pdcurses.sourceforge.net)

For changes, see the `HISTORY` file.

## Subdirectories & Boundaries
- `include`: [./include/README.md](./include/README.md) - Public PDCurses headers (`curses.h`, `panel.h`, `term.h`, `curspriv.h`).
- `nuttx`: [./nuttx/README.md](./nuttx/README.md) - NuttX framebuffer/graphic-device backend driver (`pdcscrn.c`, `pdcdisp.c`, `pdckbd.c`) for PDCurses.
- `pdcurses`: [./pdcurses/README.md](./pdcurses/README.md) - Platform-independent PDCurses core window, pad, panel, color, and input routines.

## Interface
- `[Kconfig:GRAPHICS_PDCURSES]`: Enables building the PDCurses library on NuttX.
- `[Make.defs:CONFIGURED_APPS]`: Registers `$(APPDIR)/graphics/pdcurs34` into `CONFIGURED_APPS`.
- `[Makefile:CFLAGS]`: Includes `pdcurses/Make.defs` and `nuttx/Make.defs` and exposes `graphics/pdcurs34/include`.

## Invariants
- `[Kconfig:GRAPHICS_PDCURSES]`: Selects `NXFONTS`, `NXFONTS_PACKEDMSFIRST`, and `LCD_PACKEDMSFIRST` (when `LCD` is enabled).

## Side Effects
- `[Make.defs:CONFIGURED_APPS]`: Appends `$(APPDIR)/graphics/pdcurs34` to `CONFIGURED_APPS` when `CONFIG_GRAPHICS_PDCURSES` is enabled.

## Verification
- Run: `make test`

## Legal Stuff

The core package is in the public domain, but small portions of PDCurses are
subject to copyright under various licenses. Each directory contains a `README`
file, with a section titled _Distribution Status_ which describes the status of
the files in that directory.

If you use PDCurses in an application, an acknowledgement would be appreciated,
but is not mandatory. If you make corrections or enhancements to PDCurses,
please forward them to the current maintainer for the benefit of other users.

This software is provided AS IS with NO WARRANTY whatsoever.

## Ports

PDCurses has been ported to DOS, OS/2, Win32, X11 and SDL. A directory
containing the port-specific source files exists for each of these platforms.
Build instructions are in the `README` file for each platform.

## Distribution Status

All files in this directory except configure, `config.guess` and `config.sub`
are released to the Public Domain. `config.guess` and `config.sub` are under the
GPL; configure is under a free license described within it.

## Maintainer

William McBrine <wmcbrine@users.sf.net>
