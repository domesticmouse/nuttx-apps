# `graphics/nxglyphs/include`

## Overview
Implements `graphics/nxglyphs/include` source and header components (`cursor-arrow1-16x16.h`, `cursor-arrow1-30x30.h`, `cursor-arrow2-16x16.h`, `cursor-arrow2-30x30.h` and 13 more files) in the NuttX application tree.

## Interface
- [cursor-arrow1-16x16.h:FGCOLOR1]
- [cursor-arrow1-16x16.h:FGCOLOR2]
- [cursor-arrow1-16x16.h:FGCOLOR3]
- [cursor-arrow1-30x30.h:FGCOLOR1]
- [cursor-arrow1-30x30.h:FGCOLOR2]
- [cursor-arrow1-30x30.h:FGCOLOR3]
- [cursor-arrow2-16x16.h:FGCOLOR1]
- [cursor-arrow2-16x16.h:FGCOLOR2]
- [cursor-arrow2-16x16.h:FGCOLOR3]
- [cursor-arrow2-30x30.h:FGCOLOR1]
- [cursor-arrow2-30x30.h:FGCOLOR2]
- [cursor-arrow2-30x30.h:FGCOLOR3]
- [cursor-grab-14x16.h:FGCOLOR1]
- [cursor-grab-14x16.h:FGCOLOR2]
- [cursor-grab-14x16.h:FGCOLOR3]
- [mkcursor.c:struct rgb_s]
- [mkcursor.c:main]
- [mkcursor.sh]

## Invariants
- [cursor-arrow1-16x16.h:CONFIG_NXWIDGETS_BPP]: Conditional compilation gated by `CONFIG_NXWIDGETS_BPP`.
- [cursor-arrow1-30x30.h:CONFIG_NXWIDGETS_BPP]: Conditional compilation gated by `CONFIG_NXWIDGETS_BPP`.
- [cursor-arrow2-16x16.h:CONFIG_NXWIDGETS_BPP]: Conditional compilation gated by `CONFIG_NXWIDGETS_BPP`.
- [cursor-arrow2-30x30.h:CONFIG_NXWIDGETS_BPP]: Conditional compilation gated by `CONFIG_NXWIDGETS_BPP`.
- [cursor-grab-14x16.h:CONFIG_NXWIDGETS_BPP]: Conditional compilation gated by `CONFIG_NXWIDGETS_BPP`.
- [cursor-grab-25x30.h:CONFIG_NXWIDGETS_BPP]: Conditional compilation gated by `CONFIG_NXWIDGETS_BPP`.

## Side Effects
- [mkcursor.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [mkcursor.sh]: Executes shell utilities and generates or modifies build artifacts.

## Verification
- Run: `make test`
