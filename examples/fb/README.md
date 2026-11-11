# fb

## Overview
Framebuffer driver example (`fb`). Enable the Framebuffer driver example.

## Interface
- `[Kconfig:EXAMPLES_FB]` - Build configuration option `EXAMPLES_FB`
- `[Kconfig:EXAMPLES_FB_DEFAULTFB]` - Build configuration option `EXAMPLES_FB_DEFAULTFB`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_FB_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_FB_PROGNAME}`
- `[fb_main.c:struct fb_state_s]` - Structure definition `fb_state_s`
- `[fb_main.c:main]` - Application entry point `main()`
- `[fb_main.c:getopt]` - Command-line option parser supporting flags `"p:"`

## Invariants
- `[Kconfig:depends on VIDEO_FB]` - Requires kernel/app configuration `VIDEO_FB`
- `[fb_main.c:CONFIG_FB_OVERLAY]` - Configuration guard on `CONFIG_FB_OVERLAY`
- `[fb_main.c:CONFIG_FB_UPDATE]` - Configuration guard on `CONFIG_FB_UPDATE`

## Side Effects
- `[fb_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[fb_main.c:open]` - Opens device nodes or files via `open()`
- `[fb_main.c:mmap]` - Maps device or shared memory buffers via `mmap()`
- `[fb_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
