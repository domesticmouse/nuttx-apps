# fbcon

## Overview
Framebuffer console example (`fbcon`). Enable the Framebuffer console example. This example allows STDOUT and/or STDERR to be redirected and displayed on a framebuffer character device.

## Interface
- `[Kconfig:EXAMPLES_FBCON]` - Build configuration option `EXAMPLES_FBCON`
- `[Kconfig:EXAMPLES_FBCON_PIPE_STDOUT]` - Build configuration option `EXAMPLES_FBCON_PIPE_STDOUT`
- `[Makefile:PROGNAME]` - Registers application/module target `fbcon`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `fbcon`
- `[fbcon_main.c:struct fbcon_glyph_s]` - Structure definition `fbcon_glyph_s`
- `[fbcon_main.c:struct fbcon_bitmap_s]` - Structure definition `fbcon_bitmap_s`
- `[fbcon_main.c:struct fbcon_state_s]` - Structure definition `fbcon_state_s`
- `[fbcon_main.c:struct vt100_sequence_s]` - Structure definition `vt100_sequence_s`
- `[fbcon_main.c:enum exitcode_e]` - Enumeration `exitcode_e`
- `[fbcon_main.c:enum fbcon_vt100state_e]` - Enumeration `fbcon_vt100state_e`
- `[fbcon_main.c:fbcon_newline]` - Public function `fbcon_newline()`
- `[fbcon_main.c:fbcon_putc]` - Public function `fbcon_putc()`
- `[fbcon_main.c:fbcon_fillchar]` - Public function `fbcon_fillchar()`
- `[fbcon_main.c:fbcon_vt100part]` - Public function `fbcon_vt100part()`
- `[fbcon_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on EXAMPLES_FBCON_CUSTOM_BPP]` - Requires kernel/app configuration `EXAMPLES_FBCON_CUSTOM_BPP`
- `[Kconfig:depends on !NX_DISABLE_1BPP]` - Requires kernel/app configuration `!NX_DISABLE_1BPP`
- `[Kconfig:depends on !NX_DISABLE_2BPP]` - Requires kernel/app configuration `!NX_DISABLE_2BPP`
- `[fbcon_main.c:#error]` - Compile-time precondition: This application requires NX Graphics
- `[fbcon_main.c:#error]` - Compile-time precondition: FIFO and Named Pipe Drivers should be enabled in the configuration
- `[fbcon_main.c:#error]` - Compile-time precondition: No pixel depth enabled
- `[fbcon_main.c:#error]` - Compile-time precondition: Unsupported CONFIG_EXAMPLES_FBCON_BPP
- `[fbcon_main.c:#error]` - Compile-time precondition: NXFONT_DEFAULT not defined
- `[fbcon_main.c:#error]` - Compile-time precondition: Additional logic is needed here for 24bpp support
- `[fbcon_main.c:CONFIG_NX]` - Configuration guard on `CONFIG_NX`
- `[fbcon_main.c:CONFIG_DEV_PIPE_SIZE]` - Configuration guard on `CONFIG_DEV_PIPE_SIZE`
- `[fbcon_main.c:CONFIG_NSH_CLE]` - Configuration guard on `CONFIG_NSH_CLE`
- `[fbcon_main.c:CONFIG_EXAMPLES_FBCON_PIPE_STDOUT]` - Configuration guard on `CONFIG_EXAMPLES_FBCON_PIPE_STDOUT`
- `[fbcon_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[fbcon_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[fbcon_main.c:open]` - Opens device nodes or files via `open()`
- `[fbcon_main.c:posix_spawn]` - Spawns child processes via `posix_spawn()`
- `[fbcon_main.c:mmap]` - Maps device or shared memory buffers via `mmap()`
- `[fbcon_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[fbcon_main.c:write]` - Writes bytes to file or device descriptors via `write()`

## Verification
- Run: `make test`
