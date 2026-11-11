# nxlines

## Overview
NX graphics lines example (`nxlines`). Enable the X graphics lines example

## Interface
- `[Kconfig:EXAMPLES_NXLINES]` - Build configuration option `EXAMPLES_NXLINES`
- `[Kconfig:EXAMPLES_NXLINES_PROGNAME]` - Build configuration option `EXAMPLES_NXLINES_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NXLINES_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NXLINES_PROGNAME}`
- `[nxlines.h:struct nxlines_data_s]` - Structure definition `nxlines_data_s`
- `[nxlines.h:enum exitcode_e]` - Enumeration `exitcode_e`
- `[nxlines.h:nxlines_listener]` - Public function declaration `nxlines_listener()`
- `[nxlines.h:nxlines_test]` - Public function declaration `nxlines_test()`
- `[nxlines_main.c:main]` - Application entry point `main()`
- `[nxlines_bkgd.c:nxlines_test]` - Public function `nxlines_test()`
- `[nxlines_listener.c:nxlines_listener]` - Public function `nxlines_listener()`

## Invariants
- `[Kconfig:depends on NX]` - Requires kernel/app configuration `NX`
- `[Kconfig:depends on !EXAMPLES_NXLINES_DEFAULT_COLORS]` - Requires kernel/app configuration `!EXAMPLES_NXLINES_DEFAULT_COLORS`
- `[Kconfig:depends on !EXAMPLES_NXLINES_DEFAULT_COLORS]` - Requires kernel/app configuration `!EXAMPLES_NXLINES_DEFAULT_COLORS`
- `[nxlines.h:#error]` - Compile-time precondition: NX is not enabled (CONFIG_NX)
- `[nxlines.h:#error]` - Compile-time precondition: The multi-threaded example requires MQ support (CONFIG_DISABLE_MQUEUE=n)
- `[nxlines.h:#error]` - Compile-time precondition: This example requires pthread support (CONFIG_DISABLE_PTHREAD=n)
- `[nxlines.h:#error]` - Compile-time precondition: This example depends on CONFIG_NX_BLOCKING
- `[nxlines.h:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[nxlines.h:CONFIG_EXAMPLES_NXLINES_BPP]` - Configuration guard on `CONFIG_EXAMPLES_NXLINES_BPP`
- `[nxlines.h:CONFIG_EXAMPLES_NXLINES_BGCOLOR]` - Configuration guard on `CONFIG_EXAMPLES_NXLINES_BGCOLOR`
- `[nxlines.h:CONFIG_EXAMPLES_NXLINES_LINEWIDTH]` - Configuration guard on `CONFIG_EXAMPLES_NXLINES_LINEWIDTH`
- `[nxlines_main.c:CONFIG_EXAMPLES_NXLINES_VPLANE]` - Configuration guard on `CONFIG_EXAMPLES_NXLINES_VPLANE`
- `[nxlines_main.c:CONFIG_EXAMPLES_NXLINES_DEVNO]` - Configuration guard on `CONFIG_EXAMPLES_NXLINES_DEVNO`
- `[nxlines_main.c:CONFIG_VNCSERVER]` - Configuration guard on `CONFIG_VNCSERVER`
- `[nxlines_bkgd.c:CONFIG_NX_ANTIALIASING]` - Configuration guard on `CONFIG_NX_ANTIALIASING`
- `[nxlines_bkgd.c:CONFIG_NX_XYINPUT]` - Configuration guard on `CONFIG_NX_XYINPUT`
- `[nxlines_bkgd.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`

## Side Effects
- `[nxlines_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[nxlines_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nxlines_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxlines_bkgd.c:printf]` - Writes formatted output to standard output via `printf()`
- `[nxlines_listener.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
