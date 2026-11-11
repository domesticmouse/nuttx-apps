# Graphics / `pdcurs34` PDCurses / `pdcurses` Portable Core

## Overview

This directory contains core PDCurses source code files common to all platforms.

## Interface
- `[pdc_initscr.c:initscr]` / `[pdc_initscr.c:Xinitscr]` / `[pdc_initscr.c:endwin]` / `[pdc_initscr.c:delscreen]` / `[pdc_initscr.c:resize_term]`: Screen initialization, teardown, and resize routines.
- `[pdc_window.c:newwin]` / `[pdc_window.c:delwin]` / `[pdc_window.c:subwin]` / `[pdc_window.c:derwin]` / `[pdc_window.c:mvwin]` / `[pdc_window.c:dupwin]`: Window creation, hierarchy, and lifecycle routines.
- `[pdc_refresh.c:wrefresh]` / `[pdc_refresh.c:wnoutrefresh]` / `[pdc_refresh.c:doupdate]` / `[pdc_refresh.c:redrawwin]`: Virtual-to-physical screen refresh and update routines.
- `[pdc_addch.c:waddch]` / `[pdc_addchstr.c:waddchnstr]` / `[pdc_addstr.c:waddnstr]` / `[pdc_printw.c:wprintw]` / `[pdc_insch.c:winsch]` / `[pdc_insstr.c:winsnstr]`: Character, string, and formatted output functions.
- `[pdc_getch.c:wgetch]` / `[pdc_getch.c:PDC_ungetch]` / `[pdc_getstr.c:wgetnstr]` / `[pdc_scanw.c:wscanw]`: Keyboard input, pushback buffer, and formatted input functions.
- `[pdc_color.c:start_color]` / `[pdc_color.c:init_pair]` / `[pdc_color.c:init_color]` / `[pdc_attr.c:wattrset]` / `[pdc_bkgd.c:wbkgd]` / `[pdc_border.c:wborder]`: Color pair, attribute, background, and border management.
- `[pdc_panel.c:new_panel]` / `[pdc_panel.c:update_panels]` / `[pdc_pad.c:newpad]` / `[pdc_pad.c:prefresh]` / `[pdc_slk.c:slk_init]` / `[pdc_scrdump.c:scr_dump]` / `[pdc_scrdump.c:scr_restore]`: Panels, pads, soft-label keys (SLK), and screen dump serialization.

## Invariants
- `[pdc_initscr.c:Xinitscr]`: Returns `NULL` if `SP` is already alive; calls `exit()` if `LINES < 2`, `COLS < 2`, or screen buffer allocation (`curscr`, `pdc_lastscr`, `stdscr`) fails.
- `[pdc_kernel.c:ripoffline]`: At most 5 lines can be ripped off (`linesrippedoff < 5`).
- `[pdc_slk.c:slk_init]`: Must be called prior to `initscr()` (`SP == NULL`) with `fmt` in `{0, 1, 2, 3, 55}`.
- `[pdc_color.c:init_pair]`: Requires `pdc_color_started == true`, `pair` in `[1, COLOR_PAIRS - 1]`, and `fg`/`bg` in `[first_col, COLORS - 1]`.
- `[pdc_getch.c:PDC_ungetch]`: Input pushback depth is bounded by `NUNGETCH` (`256`).

## Side Effects
- `[pdc_initscr.c:Xinitscr]` and `[pdc_initscr.c:delscreen]`: Open/close the display via `PDC_scr_open()` and allocate/free `curscr`, `pdc_lastscr`, `stdscr`, and `SP` heap structures.
- `[pdc_refresh.c:doupdate]`: Flushes dirty window lines to the display driver via `PDC_transform_line()` and updates physical cursor coordinates via `PDC_gotoyx()`.
- `[pdc_scrdump.c:scr_dump]` and `[pdc_scrdump.c:scr_restore]`: Read and write binary window dump files via `fopen`/`fwrite`/`fread`.
- `[pdc_debug.c:PDC_debug]`: Writes formatted trace output via `vsyslog(LOG_NOTICE, ...)` when `pdc_trace_on` is enabled.

## Verification
- Run: `make test`

## Building

These modules are built by the platform-specific makefiles, in the platform
directories.

## Distribution Status

The files in this directory are released to the Public Domain.

## Acknowledgements

The panel library was originally provided by
Warren Tucker <wht@n4hgf.mt-park.ga.us>
