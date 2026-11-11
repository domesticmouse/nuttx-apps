# nx

## Overview
NX graphics example (`nx`). Enable the NX graphics example

## Interface
- `[Kconfig:EXAMPLES_NX]` - Build configuration option `EXAMPLES_NX`
- `[Kconfig:EXAMPLES_NX_DEFAULT_COLORS]` - Build configuration option `EXAMPLES_NX_DEFAULT_COLORS`
- `[Makefile:PROGNAME]` - Registers application/module target `nx`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `nx`
- `[nx_internal.h:struct nxeg_glyph_s]` - Structure definition `nxeg_glyph_s`
- `[nx_internal.h:struct nxeg_bitmap_s]` - Structure definition `nxeg_bitmap_s`
- `[nx_internal.h:struct nxeg_state_s]` - Structure definition `nxeg_state_s`
- `[nx_internal.h:enum exitcode_e]` - Enumeration `exitcode_e`
- `[nx_internal.h:nx_listenerthread]` - Public function declaration `nx_listenerthread()`
- `[nx_internal.h:nxeg_kbdin]` - Public function declaration `nxeg_kbdin()`
- `[nx_internal.h:nxeg_tbkbdin]` - Public function declaration `nxeg_tbkbdin()`
- `[nx_internal.h:nxeg_filltext]` - Public function declaration `nxeg_filltext()`
- `[nx_main.c:main]` - Application entry point `main()`
- `[nx_events.c:nx_listenerthread]` - Public function `nx_listenerthread()`
- `[nx_kbdin.c:nxeg_kbdin]` - Public function `nxeg_kbdin()`
- `[nx_kbdin.c:nxeg_tbkbdin]` - Public function `nxeg_tbkbdin()`
- `[nx_kbdin.c:nxeg_filltext]` - Public function `nxeg_filltext()`

## Invariants
- `[Kconfig:depends on NX]` - Requires kernel/app configuration `NX`
- `[Kconfig:depends on !EXAMPLES_NX_DEFAULT_FONT]` - Requires kernel/app configuration `!EXAMPLES_NX_DEFAULT_FONT`
- `[Kconfig:depends on !EXAMPLES_NX_RAWWINDOWS]` - Requires kernel/app configuration `!EXAMPLES_NX_RAWWINDOWS`
- `[nx_internal.h:#error]` - Compile-time precondition: NX is not enabled (CONFIG_NX)
- `[nx_internal.h:#error]` - Compile-time precondition: The multi-threaded example requires MQ support (CONFIG_DISABLE_MQUEUE=n)
- `[nx_internal.h:#error]` - Compile-time precondition: This example requires pthread support (CONFIG_DISABLE_PTHREAD=n)
- `[nx_internal.h:#error]` - Compile-time precondition: This example depends on CONFIG_NX_BLOCKING
- `[nx_internal.h:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[nx_internal.h:CONFIG_EXAMPLES_NX_VPLANE]` - Configuration guard on `CONFIG_EXAMPLES_NX_VPLANE`
- `[nx_internal.h:CONFIG_EXAMPLES_NX_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NX_BPP`
- `[nx_internal.h:CONFIG_EXAMPLES_NX_BGCOLOR]` - Configuration guard on `CONFIG_EXAMPLES_NX_BGCOLOR`
- `[nx_main.c:CONFIG_EXAMPLES_NX_VPLANE]` - Configuration guard on `CONFIG_EXAMPLES_NX_VPLANE`
- `[nx_main.c:CONFIG_EXAMPLES_NX_DEVNO]` - Configuration guard on `CONFIG_EXAMPLES_NX_DEVNO`
- `[nx_main.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`
- `[nx_main.c:CONFIG_EXAMPLES_NX_RAWWINDOWS]` - Configuration guard on `CONFIG_EXAMPLES_NX_RAWWINDOWS`
- `[nx_events.c:CONFIG_NX_XYINPUT]` - Configuration guard on `CONFIG_NX_XYINPUT`
- `[nx_events.c:CONFIG_EXAMPLES_NX_RAWWINDOWS]` - Configuration guard on `CONFIG_EXAMPLES_NX_RAWWINDOWS`
- `[nx_events.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`
- `[nx_kbdin.c:#error]` - Compile-time precondition: Unsupported CONFIG_EXAMPLES_NX_BPP
- `[nx_kbdin.c:#error]` - Compile-time precondition: Additional logic is needed here for 24bpp support

## Side Effects
- `[nx_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nx_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nx_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nx_events.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nx_kbdin.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
