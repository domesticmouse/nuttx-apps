# pwfb

## Overview
NX Per-Window Framebuffer Text Example (`pwfb`). Enable the NX per-window framebuffer example

## Interface
- `[Kconfig:EXAMPLES_PWFB]` - Build configuration option `EXAMPLES_PWFB`
- `[Kconfig:EXAMPLES_PWFB_NWINDOWS]` - Build configuration option `EXAMPLES_PWFB_NWINDOWS`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_PWFB_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_PWFB_PROGNAME}`
- `[pwfb_internal.h:struct pwfb_window_s]` - Structure definition `pwfb_window_s`
- `[pwfb_internal.h:struct pwfb_cursor_s]` - Structure definition `pwfb_cursor_s`
- `[pwfb_internal.h:struct pwfb_state_s]` - Structure definition `pwfb_state_s`
- `[pwfb_internal.h:enum pfwb_cursor_state_s]` - Enumeration `pfwb_cursor_state_s`
- `[pwfb_internal.h:pwfb_listener]` - Public function declaration `pwfb_listener()`
- `[pwfb_internal.h:pwfb_motion]` - Public function declaration `pwfb_motion()`
- `[pwfb_main.c:main]` - Application entry point `main()`
- `[pwfb_events.c:pwfb_listener]` - Public function `pwfb_listener()`
- `[pwfb_motion.c:pwfb_motion]` - Public function `pwfb_motion()`

## Invariants
- `[Kconfig:depends on NX]` - Requires kernel/app configuration `NX`
- `[Kconfig:depends on !EXAMPLES_PWFB_DEFAULT_FONT]` - Requires kernel/app configuration `!EXAMPLES_PWFB_DEFAULT_FONT`
- `[pwfb_internal.h:#error]` - Compile-time precondition: NX is not enabled (CONFIG_NX)
- `[pwfb_internal.h:#error]` - Compile-time precondition: The multi-threaded example requires MQ support (CONFIG_DISABLE_MQUEUE=n)
- `[pwfb_internal.h:#error]` - Compile-time precondition: This example requires pthread support (CONFIG_DISABLE_PTHREAD=n)
- `[pwfb_internal.h:#error]` - Compile-time precondition: This example depends on CONFIG_NX_BLOCKING
- `[pwfb_internal.h:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[pwfb_internal.h:CONFIG_DISABLE_MQUEUE]` - Configuration guard on `CONFIG_DISABLE_MQUEUE`
- `[pwfb_internal.h:CONFIG_DISABLE_PTHREAD]` - Configuration guard on `CONFIG_DISABLE_PTHREAD`
- `[pwfb_internal.h:CONFIG_NX_BLOCKING]` - Configuration guard on `CONFIG_NX_BLOCKING`
- `[pwfb_main.c:CONFIG_NX_SWCURSOR]` - Configuration guard on `CONFIG_NX_SWCURSOR`
- `[pwfb_main.c:CONFIG_EXAMPLES_PWFB_NWINDOWS]` - Configuration guard on `CONFIG_EXAMPLES_PWFB_NWINDOWS`
- `[pwfb_main.c:CONFIG_VNCSERVER]` - Configuration guard on `CONFIG_VNCSERVER`
- `[pwfb_events.c:CONFIG_NX_XYINPUT]` - Configuration guard on `CONFIG_NX_XYINPUT`
- `[pwfb_events.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`
- `[pwfb_events.c:CONFIG_EXAMPLES_PWFB_VERBOSE]` - Configuration guard on `CONFIG_EXAMPLES_PWFB_VERBOSE`
- `[pwfb_motion.c:CONFIG_EXAMPLES_PWFB_NWINDOWS]` - Configuration guard on `CONFIG_EXAMPLES_PWFB_NWINDOWS`
- `[pwfb_motion.c:CONFIG_EXAMPLES_PWFB_VERBOSE]` - Configuration guard on `CONFIG_EXAMPLES_PWFB_VERBOSE`
- `[pwfb_motion.c:CONFIG_NX_SWCURSOR]` - Configuration guard on `CONFIG_NX_SWCURSOR`

## Side Effects
- `[pwfb_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[pwfb_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[pwfb_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[pwfb_events.c:printf]` - Writes formatted output to standard output via `printf()`
- `[pwfb_motion.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
