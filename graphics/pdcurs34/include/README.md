# `graphics/pdcurs34/include`

## Overview
Implements `graphics/pdcurs34/include` source and header components (`curspriv.h`, `term.h`) in the NuttX application tree.

## Interface
- [curspriv.h:PDC_beep]
- [curspriv.h:PDC_can_change_color]
- [curspriv.h:PDC_color_content]
- [curspriv.h:PDC_check_key]
- [curspriv.h:PDC_curs_set]
- [curspriv.h:PDC_flushinp]
- [curspriv.h:PDC_get_columns]
- [curspriv.h:PDC_get_cursor_mode]
- [curspriv.h:PDC_get_key]
- [curspriv.h:PDC_get_rows]
- [curspriv.h:PDC_gotoyx]
- [curspriv.h:PDC_init_color]
- [curspriv.h:PDC_init_pair]
- [curspriv.h:PDC_modifiers_set]
- [curspriv.h:PDC_mouse_set]
- [curspriv.h:PDC_napms]
- [curspriv.h:PDC_pair_content]
- [curspriv.h:PDC_reset_prog_mode]

## Invariants
- [curspriv.h:CONFIG_PDCURSES_DEBUG]: Conditional compilation gated by `CONFIG_PDCURSES_DEBUG`.
- [curspriv.h:CONFIG_PDCURSES_MULTITHREAD]: Conditional compilation gated by `CONFIG_PDCURSES_MULTITHREAD`.
- [curspriv.h:CONFIG_PDCURSES_WIDE]: Conditional compilation gated by `CONFIG_PDCURSES_WIDE`.
- [term.h:CONFIG_PDCURSES_MULTITHREAD]: Conditional compilation gated by `CONFIG_PDCURSES_MULTITHREAD`.

## Side Effects
- None

## Verification
- Run: `make test`
