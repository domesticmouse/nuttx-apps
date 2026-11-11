# `graphics/pdcurs34/nuttx`

## Overview
Provides 4x6 (`graphics/pdcurs34/nuttx`). Enables font ID FONTID_X11_MISC_FIXED_4X6 == 21.

## Interface
- [Kconfig:CONFIG_PDCURSES_FBDEV]
- [Kconfig:CONFIG_PDCURSES_FONT_4X6]
- [Kconfig:CONFIG_PDCURSES_FONT_5X7]
- [Kconfig:CONFIG_PDCURSES_FONT_5X8]
- [pdcnuttx.h:struct pdc_colorpair_s]
- [pdcnuttx.h:struct pdc_rgbcolor_s]
- [pdcnuttx.h:struct pdc_fbstate_s]
- [pdcnuttx.h:struct pdc_fbscreen_s]
- [pdcnuttx.h:struct pdc_termstate_s]
- [pdcnuttx.h:struct pdc_termscreen_s]
- [pdcnuttx.h:pdc_color_t]
- [pdcnuttx.h:PDC_clear_screen]
- [pdcnuttx.h:PDC_input_open]
- [pdcnuttx.h:PDC_input_close]
- [pdcclip.c:PDC_getclipboard]
- [pdcclip.c:PDC_setclipboard]
- [pdcclip.c:PDC_freeclipboard]
- [pdcclip.c:PDC_clearclipboard]

## Invariants
- [Kconfig:CONFIG_PDCURSES_FBDEV]: Build and feature compilation gated by `CONFIG_PDCURSES_FBDEV`.
- [Kconfig:CONFIG_PDCURSES_FONT_4X6]: Build and feature compilation gated by `CONFIG_PDCURSES_FONT_4X6`.
- [Kconfig:depends on PDCURSES_MONO]: Requires Kconfig dependency condition `PDCURSES_MONO`.
- [Kconfig:depends on !PDCURSES_MONO]: Requires Kconfig dependency condition `!PDCURSES_MONO`.
- [Kconfig:depends on INPUT_DJOYSTICK]: Requires Kconfig dependency condition `INPUT_DJOYSTICK`.
- [pdcnuttx.h:CONFIG_SYSTEM_TERMCURSES]: Conditional compilation gated by `CONFIG_SYSTEM_TERMCURSES`.

## Side Effects
- [pdcdisp.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [pdcdisp.c:write]: Performs VFS file or device descriptor I/O operations.
- [pdckbd.c:read]: Performs VFS file or device descriptor I/O operations.
- [pdcscrn.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [pdcscrn.c:close]: Performs VFS file or device descriptor I/O operations.
- [pdcscrn.c:free]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
