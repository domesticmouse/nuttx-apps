# pwlines

## Overview
NX Per-Window Framebuffer Graphics Example (`pwlines`). Enable the NX per-window framebuffer example

## Interface
- `[Kconfig:EXAMPLES_PWLINES]` - Build configuration option `EXAMPLES_PWLINES`
- `[Kconfig:EXAMPLES_PWLINES_DEFAULT_COLORS]` - Build configuration option `EXAMPLES_PWLINES_DEFAULT_COLORS`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_PWLINES_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_PWLINES_PROGNAME}`
- `[pwlines_internal.h:struct pwlines_window_s]` - Structure definition `pwlines_window_s`
- `[pwlines_internal.h:struct pwlines_state_s]` - Structure definition `pwlines_state_s`
- `[pwlines_internal.h:pwlines_listener]` - Public function declaration `pwlines_listener()`
- `[pwlines_internal.h:pwlines_circle]` - Public function declaration `pwlines_circle()`
- `[pwlines_internal.h:pwlines_update]` - Public function declaration `pwlines_update()`
- `[pwlines_internal.h:pwlines_motion]` - Public function declaration `pwlines_motion()`
- `[pwlines_main.c:main]` - Application entry point `main()`
- `[pwlines_events.c:pwlines_listener]` - Public function `pwlines_listener()`
- `[pwlines_motion.c:pwlines_motion]` - Public function `pwlines_motion()`
- `[pwlines_update.c:pwlines_circle]` - Public function `pwlines_circle()`
- `[pwlines_update.c:pwlines_update]` - Public function `pwlines_update()`

## Invariants
- `[Kconfig:depends on NX]` - Requires kernel/app configuration `NX`
- `[pwlines_internal.h:#error]` - Compile-time precondition: NX is not enabled (CONFIG_NX)
- `[pwlines_internal.h:#error]` - Compile-time precondition: The multi-threaded example requires MQ support (CONFIG_DISABLE_MQUEUE=n)
- `[pwlines_internal.h:#error]` - Compile-time precondition: This example requires pthread support (CONFIG_DISABLE_PTHREAD=n)
- `[pwlines_internal.h:#error]` - Compile-time precondition: This example depends on CONFIG_NX_BLOCKING
- `[pwlines_internal.h:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[pwlines_internal.h:CONFIG_DISABLE_MQUEUE]` - Configuration guard on `CONFIG_DISABLE_MQUEUE`
- `[pwlines_internal.h:CONFIG_DISABLE_PTHREAD]` - Configuration guard on `CONFIG_DISABLE_PTHREAD`
- `[pwlines_internal.h:CONFIG_NX_BLOCKING]` - Configuration guard on `CONFIG_NX_BLOCKING`
- `[pwlines_main.c:CONFIG_VNCSERVER]` - Configuration guard on `CONFIG_VNCSERVER`
- `[pwlines_events.c:CONFIG_NX_XYINPUT]` - Configuration guard on `CONFIG_NX_XYINPUT`
- `[pwlines_events.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`
- `[pwlines_events.c:CONFIG_EXAMPLES_PWLINES_VERBOSE]` - Configuration guard on `CONFIG_EXAMPLES_PWLINES_VERBOSE`
- `[pwlines_motion.c:CONFIG_EXAMPLES_PWLINES_VERBOSE]` - Configuration guard on `CONFIG_EXAMPLES_PWLINES_VERBOSE`
- `[pwlines_update.c:CONFIG_NX_ANTIALIASING]` - Configuration guard on `CONFIG_NX_ANTIALIASING`

## Side Effects
- `[pwlines_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[pwlines_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[pwlines_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[pwlines_events.c:printf]` - Writes formatted output to standard output via `printf()`
- `[pwlines_motion.c:printf]` - Writes formatted output to standard output via `printf()`
- `[pwlines_update.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
