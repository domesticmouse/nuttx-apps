# `games/NXDoom/src`

## Overview
Implements `games/NXDoom/src`: Start reading a list of file paths from the given directory which match the given glob pattern. i_end_glob() must be called on completion.

## Interface
- [aes_prng.h:prng_start]
- [aes_prng.h:prng_stop]
- [aes_prng.h:prng_random]
- [config.h:HAVE_DECL_STRCASECMP]
- [config.h:HAVE_DECL_STRNCASECMP]
- [config.h:PACKAGE_TARNAME]
- [config.h:PACKAGE_NAME]
- [config.h:PACKAGE_STRING]
- [config.h:PROGRAM_PREFIX]
- [config.h:DISABLE_SDL2MIXER]
- [config.h:DISABLE_SDL2NET]
- [d_event.h:evtype_t]
- [d_event.h:event_t]
- [d_event.h:buttoncode_t]
- [d_event.h:buttoncode2_t]
- [d_event.h:d_post_event]
- [d_event.h:d_pop_event]
- [d_iwad.h:iwad_t]
- `doom`: [./doom/README.md](./doom/README.md) - Implements `games/NXDoom/src/doom`: Called by main loop.

## Invariants
- [deh_defs.h:CONFIG_GAMES_NXDOOM_SOUND]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_SOUND`.
- [i_endoom.h:CONFIG_GAMES_NXDOOM_ENDOOM]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_ENDOOM`.
- [i_input.h:CONFIG_GAMES_NXDOOM_KEYBOARD]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_KEYBOARD`.
- [i_input.h:CONFIG_GAMES_NXDOOM_UARTKBD]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_UARTKBD`.
- [i_sound.h:CONFIG_GAMES_NXDOOM_RTTTL_MUSIC]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_RTTTL_MUSIC`.
- [net_common.h:CONFIG_GAMES_NXDOOM_NET_LOGS]: Conditional compilation gated by `CONFIG_GAMES_NXDOOM_NET_LOGS`.

## Side Effects
- [m_misc.h:fprintf]: Writes formatted diagnostic, logging, or console output.
- [net_common.h:syslog]: Writes formatted diagnostic, logging, or console output.
- [d_dedicated.c:printf]: Writes formatted diagnostic, logging, or console output.
- [d_iwad.c:free]: Allocates or releases dynamic heap memory.
- [d_loop.c:free]: Allocates or releases dynamic heap memory.
- [d_loop.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
