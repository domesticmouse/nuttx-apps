# `games/NXDoom/src/doom`

## Overview
Implements `games/NXDoom/src/doom`: Called by main loop.

## Interface
- [am_map.h:am_responder]
- [am_map.h:am_ticker]
- [am_map.h:am_drawer]
- [am_map.h:am_stop]
- [am_map.h:AM_MSGHEADER]
- [am_map.h:AM_MSGENTERED]
- [am_map.h:AM_MSGEXITED]
- [d_englsh.h:D_DEVSTR]
- [d_englsh.h:D_CDROM]
- [d_englsh.h:PRESSKEY]
- [d_englsh.h:PRESSYN]
- [d_englsh.h:QUITMSG]
- [d_englsh.h:LOADNET]
- [d_englsh.h:QLOADNET]
- [d_englsh.h:QSAVESPOT]
- [d_englsh.h:SAVEDEAD]
- [d_items.h:weaponinfo_t]
- [d_main.h:d_process_events]

## Invariants
- [dstrings.h:CONFIG_GAMES_NXDOOM_LANG_EN]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_LANG_EN`.
- [f_wipe.h:CONFIG_GAMES_NXDOOM_NOWIPE]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_NOWIPE`.
- [info.h:CONFIG_GAMES_NXDOOM_SOUND]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_SOUND`.
- [d_main.c:CONFIG_GAMES_NXDOOM_SOUND]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_SOUND`.
- [d_main.c:CONFIG_GAMES_NXDOOM_NET]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_NET`.
- [d_main.c:CONFIG_GAMES_NXDOOM_SHOWDISKICON]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_SHOWDISKICON`.

## Side Effects
- [am_map.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [d_main.c:free]: Allocates or releases dynamic heap memory.
- [d_main.c:printf]: Writes formatted diagnostic, logging, or console output.
- [d_net.c:printf]: Writes formatted diagnostic, logging, or console output.
- [g_game.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [m_menu.c:fopen]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
