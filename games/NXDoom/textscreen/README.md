# `games/NXDoom/textscreen`

## Overview
Implements `games/NXDoom/textscreen` source and header components (`textscreen.h`, `txt_button.c`, `txt_button.h`, `txt_checkbox.c` and 41 more files) in the NuttX application tree.

## Interface
- [txt_button.h:struct txt_button_s]
- [txt_button.h:txt_new_button]
- [txt_button.h:txt_new_button2]
- [txt_button.h:txt_set_button_label]
- [txt_checkbox.h:struct txt_checkbox_s]
- [txt_checkbox.h:txt_new_check_box]
- [txt_checkbox.h:txt_new_inverted_checkbox]
- [txt_conditional.h:txt_conditional_t]
- [txt_conditional.h:txt_new_conidtional]
- [txt_conditional.h:txt_if]
- [txt_desktop.h:txt_add_desktop_window]
- [txt_desktop.h:txt_remove_desktop_window]
- [txt_desktop.h:txt_draw_desktop]
- [txt_desktop.h:txt_dispatch_events]
- [txt_desktop.h:txt_draw_window]
- [txt_desktop.h:txt_set_window_focus]
- [txt_desktop.h:txt_window_keypress]
- [txt_desktop.h:txt_set_desktop_title]
- `fonts`: [./fonts/README.md](./fonts/README.md) - Implements `games/NXDoom/textscreen/fonts` source and header components (`codepage.h`, `large.h`, `normal.h`, `small.h`) in the NuttX application tree.

## Invariants
- None

## Side Effects
- [txt_button.c:free]: Allocates or releases dynamic heap memory.
- [txt_checkbox.c:free]: Allocates or releases dynamic heap memory.
- [txt_conditional.c:malloc]: Allocates or releases dynamic heap memory.
- [txt_desktop.c:free]: Allocates or releases dynamic heap memory.
- [txt_dropdown.c:free]: Allocates or releases dynamic heap memory.
- [txt_fileselect.c:read]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
