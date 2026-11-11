# nanoxterm

## Overview
Nano-X terminal emulator example (`nanoxterm`). Enable the Nano-X terminal emulator example application.  It is a port of the nxterm demo from Microwindows.  It starts the Nano-X server, connects to it and creates a terminal window that runs an NSH shell instance on a pseudo terminal.

## Interface
- `[Kconfig:EXAMPLES_NANOXTERM]` - Build configuration option `EXAMPLES_NANOXTERM`
- `[Kconfig:EXAMPLES_NANOXTERM_PROGNAME]` - Build configuration option `EXAMPLES_NANOXTERM_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NANOXTERM_PROGNAME)`
- `[nxterm.c:sflush]` - Public function `sflush()`
- `[nxterm.c:lineRedraw]` - Public function `lineRedraw()`
- `[nxterm.c:sadd]` - Public function `sadd()`
- `[nxterm.c:show_cursor]` - Public function `show_cursor()`
- `[nxterm.c:draw_cursor]` - Public function `draw_cursor()`
- `[nxterm.c:hide_cursor]` - Public function `hide_cursor()`
- `[nxterm.c:vscrollup]` - Public function `vscrollup()`
- `[nxterm.c:vscrolldown]` - Public function `vscrolldown()`
- `[nxterm.c:esc5]` - Public function `esc5()`
- `[nxterm.c:esc4]` - Public function `esc4()`
- `[nxterm.c:esc3]` - Public function `esc3()`
- `[nxterm.c:esc2]` - Public function `esc2()`
- `[nxterm.c:esc1]` - Public function `esc1()`
- `[nxterm.c:pos_xaxis]` - Public function `pos_xaxis()`
- `[nxterm.c:pos_yaxis]` - Public function `pos_yaxis()`
- `[nxterm.c:rendition]` - Public function `rendition()`
- `[nxterm.c:esc100]` - Public function `esc100()`
- `[nxterm.c:esc0]` - Public function `esc0()`
- `[nxterm.c:printc]` - Public function `printc()`
- `[nxterm.c:init]` - Public function `init()`
- `[nxterm.c:term]` - Public function `term()`
- `[nxterm.c:do_special_key]` - Public function `do_special_key()`
- `[nxterm.c:do_special_key_ansi]` - Public function `do_special_key_ansi()`
- `[nxterm.c:usage]` - Public function `usage()`
- `[nxterm.c:main]` - Application entry point `main()`
- `[nxterm.c:term_init]` - Public function `term_init()`

## Invariants
- `[Kconfig:depends on MICROWINDOWS_NANOX && PSEUDOTERM && LIBC_EXECFUNCS]` - Requires kernel/app configuration `MICROWINDOWS_NANOX && PSEUDOTERM && LIBC_EXECFUNCS`

## Side Effects
- `[nxterm.c:open]` - Opens device nodes or files via `open()`
- `[nxterm.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[nxterm.c:posix_spawn]` - Spawns child processes via `posix_spawn()`
- `[nxterm.c:sigaction]` - Registers signal handlers via `sigaction()`
- `[nxterm.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[nxterm.c:write]` - Writes bytes to file or device descriptors via `write()`

## Verification
- Run: `make test`
