# nximage

## Overview
NX graphics image example (`nximage`). Enable the X graphics image example

## Interface
- `[Kconfig:EXAMPLES_NXIMAGE]` - Build configuration option `EXAMPLES_NXIMAGE`
- `[Kconfig:EXAMPLES_NXIMAGE_PROGNAME]` - Build configuration option `EXAMPLES_NXIMAGE_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NXIMAGE_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NXIMAGE_PROGNAME}`
- `[nximage.h:struct nximage_data_s]` - Structure definition `nximage_data_s`
- `[nximage.h:enum exitcode_e]` - Enumeration `exitcode_e`
- `[nximage.h:nximage_listener]` - Public function declaration `nximage_listener()`
- `[nximage.h:nximage_image]` - Public function declaration `nximage_image()`
- `[nximage.h:nximage_bgcolor]` - Public function declaration `nximage_bgcolor()`
- `[nximage.h:nximage_avgcolor]` - Public function declaration `nximage_avgcolor()`
- `[nximage.h:nximage_blitrow]` - Public function declaration `nximage_blitrow()`
- `[nximage_main.c:main]` - Application entry point `main()`
- `[nximage_bitmap.c:struct pix_run_s]` - Structure definition `pix_run_s`
- `[nximage_bitmap.c:nximage_bgcolor]` - Public function `nximage_bgcolor()`
- `[nximage_bitmap.c:nximage_avgcolor]` - Public function `nximage_avgcolor()`
- `[nximage_bitmap.c:nximage_blitrow]` - Public function `nximage_blitrow()`
- `[nximage_bkgd.c:struct nximage_run_s]` - Structure definition `nximage_run_s`
- `[nximage_bkgd.c:nximage_image]` - Public function `nximage_image()`
- `[nximage_listener.c:nximage_listener]` - Public function `nximage_listener()`

## Invariants
- `[Kconfig:depends on NX]` - Requires kernel/app configuration `NX`
- `[nximage.h:#error]` - Compile-time precondition: NX is not enabled (CONFIG_NX)
- `[nximage.h:#error]` - Compile-time precondition: The multi-threaded example requires MQ support (CONFIG_DISABLE_MQUEUE=n)
- `[nximage.h:#error]` - Compile-time precondition: This example requires pthread support (CONFIG_DISABLE_PTHREAD=n)
- `[nximage.h:#error]` - Compile-time precondition: This example depends on CONFIG_NX_BLOCKING
- `[nximage.h:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[nximage.h:CONFIG_EXAMPLES_NXIMAGE_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NXIMAGE_BPP`
- `[nximage.h:CONFIG_EXAMPLES_NXIMAGE_XSCALE]` - Configuration guard on `CONFIG_EXAMPLES_NXIMAGE_XSCALE`
- `[nximage.h:CONFIG_EXAMPLES_NXIMAGE_YSCALE]` - Configuration guard on `CONFIG_EXAMPLES_NXIMAGE_YSCALE`
- `[nximage_main.c:CONFIG_VNCSERVER]` - Configuration guard on `CONFIG_VNCSERVER`
- `[nximage_bitmap.c:#error]` - Compile-time precondition: 24-bit greyscale not supported
- `[nximage_bitmap.c:#error]` - Compile-time precondition: 16-bit greyscale not supported
- `[nximage_bitmap.c:#error]` - Compile-time precondition: Unsupported pixel format
- `[nximage_bitmap.c:CONFIG_EXAMPLES_NXIMAGE_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NXIMAGE_BPP`
- `[nximage_bitmap.c:CONFIG_EXAMPLES_NXIMAGE_GREYSCALE]` - Configuration guard on `CONFIG_EXAMPLES_NXIMAGE_GREYSCALE`
- `[nximage_bitmap.c:CONFIG_EXAMPLES_NXIMAGE_XSCALE]` - Configuration guard on `CONFIG_EXAMPLES_NXIMAGE_XSCALE`
- `[nximage_bitmap.c:DEBUGASSERT]` - Runtime state and non-null pointer assertions via `DEBUGASSERT()`
- `[nximage_bkgd.c:#error]` - Compile-time precondition: Unsupported CONFIG_EXAMPLES_NXIMAGE_BPP
- `[nximage_bkgd.c:CONFIG_EXAMPLES_NXIMAGE_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NXIMAGE_BPP`
- `[nximage_bkgd.c:CONFIG_EXAMPLES_NXIMAGE_YSCALE]` - Configuration guard on `CONFIG_EXAMPLES_NXIMAGE_YSCALE`

## Side Effects
- `[nximage_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nximage_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nximage_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nximage_bkgd.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nximage_listener.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
