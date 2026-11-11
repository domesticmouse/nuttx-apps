# `include/graphics`

## Overview
Implements `include/graphics`: Start a new display list. This function will:

## Interface
- [curses.h:struct _win]
- [curses.h:struct SLK]
- [curses.h:struct cttyset]
- [curses.h:struct pdc_context_s]
- [curses.h:MOUSE_STATUS]
- [curses.h:MEVENT]
- [curses.h:WINDOW]
- [curses.h:SCREEN]
- [curses.h:RIPPEDOFFLINE]
- [curses.h:chtype]
- [curses.h:cchar_t]
- [curses.h:attr_t]
- [curses.h:mmask_t]
- [curses.h:PDC_ctx]
- [curses.h:PDC_ctx_free]
- [curses.h:pdc_alloc_panel_ctx]
- [curses.h:pdc_alloc_term_ctx]
- [curses.h:addch]

## Invariants
- [curses.h:CONFIG_PDCURSES_WIDE]: Conditional compilation gated by `CONFIG_PDCURSES_WIDE`.
- [curses.h:CONFIG_PDCURSES_CHTYPE_LONG]: Conditional compilation gated by `CONFIG_PDCURSES_CHTYPE_LONG`.
- [curses.h:CONFIG_PDCURSES_SHORT_ALTCHARSET]: Conditional compilation gated by `CONFIG_PDCURSES_SHORT_ALTCHARSET`.
- [curses.h:CONFIG_PDCURSES_MULTITHREAD]: Conditional compilation gated by `CONFIG_PDCURSES_MULTITHREAD`.
- [curses.h:CONFIG_PDCURSES_MULTITHREAD_HASH]: Conditional compilation gated by `CONFIG_PDCURSES_MULTITHREAD_HASH`.
- [curses.h:CONFIG_SYSTEM_TERMCURSES]: Conditional compilation gated by `CONFIG_SYSTEM_TERMCURSES`.

## Side Effects
- None

## Verification
- Run: `make test`
