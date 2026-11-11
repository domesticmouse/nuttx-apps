# nxhello

## Overview
NX graphics "Hello, World!" example (`nxhello`). Enable the NX graphics "Hello, World!" example

## Interface
- `[Kconfig:EXAMPLES_NXHELLO]` - Build configuration option `EXAMPLES_NXHELLO`
- `[Kconfig:EXAMPLES_NXHELLO_PROGNAME]` - Build configuration option `EXAMPLES_NXHELLO_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NXHELLO_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NXHELLO_PROGNAME}`
- `[nxhello.h:struct nxhello_glyph_s]` - Structure definition `nxhello_glyph_s`
- `[nxhello.h:struct nxhello_bitmap_s]` - Structure definition `nxhello_bitmap_s`
- `[nxhello.h:struct nxhello_data_s]` - Structure definition `nxhello_data_s`
- `[nxhello.h:enum exitcode_e]` - Enumeration `exitcode_e`
- `[nxhello.h:nxhello_listener]` - Public function declaration `nxhello_listener()`
- `[nxhello.h:nxhello_hello]` - Public function declaration `nxhello_hello()`
- `[nxhello_main.c:main]` - Application entry point `main()`
- `[nxhello_bkgd.c:nxhello_hello]` - Public function `nxhello_hello()`
- `[nxhello_listener.c:nxhello_listener]` - Public function `nxhello_listener()`

## Invariants
- `[Kconfig:depends on NX]` - Requires kernel/app configuration `NX`
- `[Kconfig:depends on config EXAMPLES_NXHELLO_BPP.]` - Requires kernel/app configuration `config EXAMPLES_NXHELLO_BPP.`
- `[nxhello.h:#error]` - Compile-time precondition: NX is not enabled (CONFIG_NX)
- `[nxhello.h:#error]` - Compile-time precondition: Only CONFIG_NX_NPLANES==1 supported
- `[nxhello.h:#error]` - Compile-time precondition: The multi-threaded example requires MQ support (CONFIG_DISABLE_MQUEUE=n)
- `[nxhello.h:#error]` - Compile-time precondition: This example requires pthread support (CONFIG_DISABLE_PTHREAD=n)
- `[nxhello.h:#error]` - Compile-time precondition: This example depends on CONFIG_NX_BLOCKING
- `[nxhello.h:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[nxhello.h:CONFIG_NX_NPLANES]` - Configuration guard on `CONFIG_NX_NPLANES`
- `[nxhello.h:CONFIG_EXAMPLES_NXHELLO_BGCOLOR]` - Configuration guard on `CONFIG_EXAMPLES_NXHELLO_BGCOLOR`
- `[nxhello.h:CONFIG_EXAMPLES_NXHELLO_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NXHELLO_BPP`
- `[nxhello_main.c:CONFIG_VNCSERVER]` - Configuration guard on `CONFIG_VNCSERVER`
- `[nxhello_bkgd.c:#error]` - Compile-time precondition: Unsupported CONFIG_EXAMPLES_NXHELLO_BPP
- `[nxhello_bkgd.c:#error]` - Compile-time precondition: Additional logic is needed here for 24bpp support
- `[nxhello_bkgd.c:CONFIG_EXAMPLES_NXHELLO_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NXHELLO_BPP`
- `[nxhello_bkgd.c:CONFIG_NX_XYINPUT]` - Configuration guard on `CONFIG_NX_XYINPUT`
- `[nxhello_bkgd.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`
- `[nxhello_bkgd.c:CONFIG_NX_NPLANES]` - Configuration guard on `CONFIG_NX_NPLANES`

## Side Effects
- `[nxhello_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nxhello_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nxhello_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxhello_bkgd.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxhello_listener.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
