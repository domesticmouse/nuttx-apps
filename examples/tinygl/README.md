# tinygl

## Overview
TinyGL gears demo (`tinygl`). Render the classic OpenGL "gears" demo with TinyGL on a framebuffer device.  The framebuffer must use the same pixel format as TinyGL (RGB32 or RGB565, see CONFIG_TINYGL_RENDER_BITS_*).

## Interface
- `[Kconfig:EXAMPLES_TINYGL]` - Build configuration option `EXAMPLES_TINYGL`
- `[Kconfig:EXAMPLES_TINYGL_DEFAULTFB]` - Build configuration option `EXAMPLES_TINYGL_DEFAULTFB`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_TINYGL_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_TINYGL_PROGNAME}`
- `[tinygl_main.c:struct tinygl_fb_s]` - Structure definition `tinygl_fb_s`
- `[tinygl_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on GRAPHICS_TINYGL && VIDEO_FB]` - Requires kernel/app configuration `GRAPHICS_TINYGL && VIDEO_FB`
- `[tinygl_main.c:CONFIG_FB_UPDATE]` - Configuration guard on `CONFIG_FB_UPDATE`
- `[tinygl_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[tinygl_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[tinygl_main.c:open]` - Opens device nodes or files via `open()`
- `[tinygl_main.c:mmap]` - Maps device or shared memory buffers via `mmap()`
- `[tinygl_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
