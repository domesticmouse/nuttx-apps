# nxdemo

## Overview
NX Demo "Graphic test" example (`nxdemo`). Enable the NX graphics "Demo Test" example

## Interface
- `[Kconfig:EXAMPLES_NXDEMO]` - Build configuration option `EXAMPLES_NXDEMO`
- `[Kconfig:EXAMPLES_NXDEMO_VPLANE]` - Build configuration option `EXAMPLES_NXDEMO_VPLANE`
- `[Makefile:PROGNAME]` - Registers application/module target `nxdemo`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `nxdemo`
- `[nxdemo.h:struct nxdemo_glyph_s]` - Structure definition `nxdemo_glyph_s`
- `[nxdemo.h:struct nxdemo_bitmap_s]` - Structure definition `nxdemo_bitmap_s`
- `[nxdemo.h:struct nxdemo_data_s]` - Structure definition `nxdemo_data_s`
- `[nxdemo.h:enum exitcode_e]` - Enumeration `exitcode_e`
- `[nxdemo.h:nxdemo_listener]` - Public function declaration `nxdemo_listener()`
- `[nxdemo.h:nxdemo_hello]` - Public function declaration `nxdemo_hello()`
- `[nxdemo_main.c:main]` - Application entry point `main()`
- `[nxdemo_bkgd.c:nxdemo_hello]` - Public function `nxdemo_hello()`
- `[nxdemo_listener.c:nxdemo_listener]` - Public function `nxdemo_listener()`

## Invariants
- `[Kconfig:depends on BOARDCTL]` - Requires kernel/app configuration `BOARDCTL`
- `[nxdemo.h:#error]` - Compile-time precondition: NX is not enabled (CONFIG_NX)
- `[nxdemo.h:#error]` - Compile-time precondition: The multi-threaded example requires MQ support (CONFIG_DISABLE_MQUEUE=n)
- `[nxdemo.h:#error]` - Compile-time precondition: This example requires pthread support (CONFIG_DISABLE_PTHREAD=n)
- `[nxdemo.h:#error]` - Compile-time precondition: This example depends on CONFIG_NX_BLOCKING
- `[nxdemo.h:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[nxdemo.h:CONFIG_EXAMPLES_NXDEMO_VPLANE]` - Configuration guard on `CONFIG_EXAMPLES_NXDEMO_VPLANE`
- `[nxdemo.h:CONFIG_EXAMPLES_NXDEMO_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NXDEMO_BPP`
- `[nxdemo.h:CONFIG_EXAMPLES_NXDEMO_BGCOLOR]` - Configuration guard on `CONFIG_EXAMPLES_NXDEMO_BGCOLOR`
- `[nxdemo_main.c:CONFIG_NX_LCDDRIVER]` - Configuration guard on `CONFIG_NX_LCDDRIVER`
- `[nxdemo_main.c:CONFIG_EXAMPLES_NXDEMO_VPLANE]` - Configuration guard on `CONFIG_EXAMPLES_NXDEMO_VPLANE`
- `[nxdemo_main.c:CONFIG_EXAMPLES_NXDEMO_DEVNO]` - Configuration guard on `CONFIG_EXAMPLES_NXDEMO_DEVNO`
- `[nxdemo_main.c:CONFIG_VNCSERVER]` - Configuration guard on `CONFIG_VNCSERVER`
- `[nxdemo_bkgd.c:#error]` - Compile-time precondition: Unsupported CONFIG_EXAMPLES_NXDEMO_BPP
- `[nxdemo_bkgd.c:CONFIG_EXAMPLES_NXDEMO_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NXDEMO_BPP`
- `[nxdemo_bkgd.c:CONFIG_NX_XYINPUT]` - Configuration guard on `CONFIG_NX_XYINPUT`
- `[nxdemo_bkgd.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`

## Side Effects
- `[nxdemo_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nxdemo_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nxdemo_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxdemo_bkgd.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxdemo_listener.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
