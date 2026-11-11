# fboverlay

## Overview
Framebuffer overlay test tool (`fboverlay`). Enable framebuffer overlay test.

## Interface
- `[Kconfig:EXAMPLES_FBOVERLAY]` - Build configuration option `EXAMPLES_FBOVERLAY`
- `[Kconfig:EXAMPLES_FBOVERLAY_PROGNAME]` - Build configuration option `EXAMPLES_FBOVERLAY_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_FBOVERLAY_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_FBOVERLAY_PROGNAME}`
- `[fboverlay_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on FB_OVERLAY]` - Requires kernel/app configuration `FB_OVERLAY`
- `[fboverlay_main.c:CONFIG_FB_CMAP]` - Configuration guard on `CONFIG_FB_CMAP`
- `[fboverlay_main.c:CONFIG_FB_FMT_RGB16_565]` - Configuration guard on `CONFIG_FB_FMT_RGB16_565`
- `[fboverlay_main.c:CONFIG_CMAP_TRANSPARENCY]` - Configuration guard on `CONFIG_CMAP_TRANSPARENCY`
- `[fboverlay_main.c:CONFIG_FB_SYNC]` - Configuration guard on `CONFIG_FB_SYNC`
- `[fboverlay_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[fboverlay_main.c:/dev/fb0]` - Opens or interacts with VFS/device path `/dev/fb0`
- `[fboverlay_main.c:/dev/fb0\]` - Opens or interacts with VFS/device path `/dev/fb0\`
- `[fboverlay_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[fboverlay_main.c:open]` - Opens device nodes or files via `open()`
- `[fboverlay_main.c:mmap]` - Maps device or shared memory buffers via `mmap()`
- `[fboverlay_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
