# nxtext

## Overview
NX graphics text example (`nxtext`). Enable the NX graphics text example

## Interface
- `[Kconfig:EXAMPLES_NXTEXT]` - Build configuration option `EXAMPLES_NXTEXT`
- `[Kconfig:EXAMPLES_NXTEXT_BPP]` - Build configuration option `EXAMPLES_NXTEXT_BPP`
- `[Makefile:PROGNAME]` - Registers application/module target `nxtext`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `nxtext`
- `[nxtext_internal.h:struct nxtext_glyph_s]` - Structure definition `nxtext_glyph_s`
- `[nxtext_internal.h:struct nxtext_bitmap_s]` - Structure definition `nxtext_bitmap_s`
- `[nxtext_internal.h:struct nxtext_state_s]` - Structure definition `nxtext_state_s`
- `[nxtext_internal.h:enum exitcode_e]` - Enumeration `exitcode_e`
- `[nxtext_internal.h:nxtext_listener]` - Public function declaration `nxtext_listener()`
- `[nxtext_internal.h:nxbg_getstate]` - Public function declaration `nxbg_getstate()`
- `[nxtext_internal.h:nxbg_write]` - Public function declaration `nxbg_write()`
- `[nxtext_internal.h:nxpu_open]` - Public function declaration `nxpu_open()`
- `[nxtext_internal.h:nxpu_close]` - Public function declaration `nxpu_close()`
- `[nxtext_internal.h:nxtext_home]` - Public function declaration `nxtext_home()`
- `[nxtext_internal.h:nxtext_newline]` - Public function declaration `nxtext_newline()`
- `[nxtext_internal.h:nxtext_putc]` - Public function declaration `nxtext_putc()`
- `[nxtext_internal.h:nxtext_fillchar]` - Public function declaration `nxtext_fillchar()`
- `[nxtext_main.c:main]` - Application entry point `main()`
- `[nxtext_bkgd.c:nxbg_getstate]` - Public function `nxbg_getstate()`
- `[nxtext_bkgd.c:nxbg_write]` - Public function `nxbg_write()`
- `[nxtext_listener.c:nxtext_listener]` - Public function `nxtext_listener()`
- `[nxtext_popup.c:nxpu_open]` - Public function `nxpu_open()`
- `[nxtext_popup.c:nxpu_close]` - Public function `nxpu_close()`
- `[nxtext_putc.c:nxtext_home]` - Public function `nxtext_home()`
- `[nxtext_putc.c:nxtext_newline]` - Public function `nxtext_newline()`
- `[nxtext_putc.c:nxtext_putc]` - Public function `nxtext_putc()`
- `[nxtext_putc.c:nxtext_fillchar]` - Public function `nxtext_fillchar()`

## Invariants
- `[Kconfig:depends on NX]` - Requires kernel/app configuration `NX`
- `[Kconfig:depends on config EXAMPLES_NXTEXT_BPP.]` - Requires kernel/app configuration `config EXAMPLES_NXTEXT_BPP.`
- `[Kconfig:depends on config EXAMPLES_NXTEXT_BPP.]` - Requires kernel/app configuration `config EXAMPLES_NXTEXT_BPP.`
- `[nxtext_internal.h:#error]` - Compile-time precondition: NX is not enabled (CONFIG_NX)
- `[nxtext_internal.h:#error]` - Compile-time precondition: No pixel depth provided
- `[nxtext_internal.h:#error]` - Compile-time precondition: The multi-threaded example requires MQ support (CONFIG_DISABLE_MQUEUE=n)
- `[nxtext_internal.h:#error]` - Compile-time precondition: This example requires pthread support (CONFIG_DISABLE_PTHREAD=n)
- `[nxtext_internal.h:#error]` - Compile-time precondition: This example depends on CONFIG_NX_BLOCKING
- `[nxtext_internal.h:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[nxtext_internal.h:CONFIG_EXAMPLES_NXTEXT_VPLANE]` - Configuration guard on `CONFIG_EXAMPLES_NXTEXT_VPLANE`
- `[nxtext_internal.h:CONFIG_EXAMPLES_NXTEXT_LINESPACING]` - Configuration guard on `CONFIG_EXAMPLES_NXTEXT_LINESPACING`
- `[nxtext_internal.h:CONFIG_EXAMPLES_NXTEXT_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NXTEXT_BPP`
- `[nxtext_main.c:CONFIG_NX_LCDDRIVER]` - Configuration guard on `CONFIG_NX_LCDDRIVER`
- `[nxtext_main.c:CONFIG_EXAMPLES_NXTEXT_VPLANE]` - Configuration guard on `CONFIG_EXAMPLES_NXTEXT_VPLANE`
- `[nxtext_main.c:CONFIG_EXAMPLES_NXTEXT_DEVNO]` - Configuration guard on `CONFIG_EXAMPLES_NXTEXT_DEVNO`
- `[nxtext_main.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`
- `[nxtext_bkgd.c:CONFIG_NX_XYINPUT]` - Configuration guard on `CONFIG_NX_XYINPUT`
- `[nxtext_bkgd.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`
- `[nxtext_popup.c:CONFIG_NX_XYINPUT]` - Configuration guard on `CONFIG_NX_XYINPUT`
- `[nxtext_popup.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`

## Side Effects
- `[nxtext_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nxtext_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nxtext_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxtext_bkgd.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxtext_listener.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxtext_popup.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxtext_putc.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
