# `graphics/nxglyphs/src`

## Overview
Implements `graphics/nxglyphs/src` source and header components (`glpyh_menu2-21x21.cxx`, `glpyh_menu2-42x42.cxx`, `glpyh_minimize2-21x21.cxx`, `glpyh_minimize2-42x42.cxx` and 57 more files) in the NuttX application tree.

## Interface
- [mksrle.c:struct rgb_s]
- [mksrle.c:main]
- [mksrle.sh]

## Invariants
- [glpyh_menu2-21x21.cxx:CONFIG_NXWIDGETS_BPP]: Conditional compilation gated by `CONFIG_NXWIDGETS_BPP`.
- [glpyh_menu2-21x21.cxx:CONFIG_NXWIDGETS_GREYSCALE]: Conditional compilation gated by `CONFIG_NXWIDGETS_GREYSCALE`.
- [glpyh_menu2-42x42.cxx:CONFIG_NXWIDGETS_BPP]: Conditional compilation gated by `CONFIG_NXWIDGETS_BPP`.
- [glpyh_menu2-42x42.cxx:CONFIG_NXWIDGETS_GREYSCALE]: Conditional compilation gated by `CONFIG_NXWIDGETS_GREYSCALE`.
- [glpyh_minimize2-21x21.cxx:CONFIG_NXWIDGETS_BPP]: Conditional compilation gated by `CONFIG_NXWIDGETS_BPP`.
- [glpyh_minimize2-21x21.cxx:CONFIG_NXWIDGETS_GREYSCALE]: Conditional compilation gated by `CONFIG_NXWIDGETS_GREYSCALE`.

## Side Effects
- [mksrle.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [mksrle.sh]: Executes shell utilities and generates or modifies build artifacts.

## Verification
- Run: `make test`
