# Music Macro Language Parser (`audioutils/mml_parser`)

## Overview
Implements a stateful Music Macro Language (MML) score string parser (`CONFIG_AUDIOUTILS_MMLPARSER_LIB`) that converts ASCII musical notation (notes, rests, octaves, tempo, volume, tuplets, and chords) into note indices and PCM sample counts.

## Interface
- `[mml_parser.c:init_mml]`: Initializes an `struct music_macro_lang_s` parser state with sampling frequency, default tempo, octave, and note length.
- `[mml_parser.c:parse_mml]`: Parses the next MML token from `*score` and populates an `struct mml_result_s` result descriptor.
- `[Kconfig:CONFIG_AUDIOUTILS_MMLPARSER_LIB]`: Enables building the MML parser library.

## Invariants
- `[mml_parser.c:calc_samples]`: Note length denominator `num` must be in `{0, 1, 2, 4, 8, 16, 32, 64}` and `dots <= 4`; otherwise returns `-EINVAL`.
- `[mml_parser.c:handle_volume]`: Volume value must be within `[0, 100]`; otherwise returns `MML_TYPE_VOLUME_ERROR`.
- `[mml_parser.c:handle_starttuplet]`, `[mml_parser.c:handle_stoptuplet]`, and `[mml_parser.c:handle_tupletnote]`: Disallow nested tuplets (`mml->state` must be `MML_STATE_NORMAL`), require `tuplet_notes > 0`, and enforce exact note count (`mml->cur_tuplet == mml->tuplet_notes`) when closing a tuplet.
- `[mml_parser.c:handle_startchord]`: Ignores chord notes beyond `MAX_CHORD_NOTES` and returns `MML_TYPE_CHORD_ERROR` if `'\\0'` is encountered before `']'`.

## Side Effects
- `[mml_parser.c:init_mml]` and `[mml_parser.c:parse_mml]`: Mutate the caller-supplied `*mml` state structure, advance the caller's `*score` character pointer, and populate `*result`.

## Verification
- Run: `make test`
