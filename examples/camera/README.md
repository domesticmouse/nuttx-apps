# camera

## Overview
Camera example (`camera`). Enable the camera example

## Interface
- `[Kconfig:EXAMPLES_CAMERA]` - Build configuration option `EXAMPLES_CAMERA`
- `[Kconfig:EXAMPLES_CAMERA_PROGNAME]` - Build configuration option `EXAMPLES_CAMERA_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_CAMERA_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_CAMERA_PROGNAME}`
- `[camera_bkgd.h:nximage_initialize]` - Public function declaration `nximage_initialize()`
- `[camera_bkgd.h:nximage_draw]` - Public function declaration `nximage_draw()`
- `[camera_bkgd.h:nximage_finalize]` - Public function declaration `nximage_finalize()`
- `[camera_fileutil.h:futil_initialize]` - Public function declaration `futil_initialize()`
- `[camera_fileutil.h:futil_writeimage]` - Public function declaration `futil_writeimage()`
- `[camera_main.c:struct v_buffer]` - Structure definition `v_buffer`
- `[camera_main.c:main]` - Application entry point `main()`
- `[camera_bkgd.c:struct nximage_data_s]` - Structure definition `nximage_data_s`
- `[camera_bkgd.c:nximage_initialize]` - Public function `nximage_initialize()`
- `[camera_bkgd.c:nximage_draw]` - Public function `nximage_draw()`
- `[camera_bkgd.c:nximage_finalize]` - Public function `nximage_finalize()`
- `[camera_fileutil.c:futil_initialize]` - Public function `futil_initialize()`
- `[camera_fileutil.c:futil_writeimage]` - Public function `futil_writeimage()`

## Invariants
- `[Kconfig:depends on DRIVERS_VIDEO]` - Requires kernel/app configuration `DRIVERS_VIDEO`
- `[camera_main.c:CONFIG_EXAMPLES_CAMERA_OUTPUT_LCD]` - Configuration guard on `CONFIG_EXAMPLES_CAMERA_OUTPUT_LCD`
- `[camera_bkgd.c:CONFIG_NX_XYINPUT]` - Configuration guard on `CONFIG_NX_XYINPUT`
- `[camera_bkgd.c:CONFIG_NX_KBD]` - Configuration guard on `CONFIG_NX_KBD`

## Side Effects
- `[camera_main.c:/dev/video]` - Opens or interacts with VFS/device path `/dev/video`
- `[camera_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[camera_main.c:open]` - Opens device nodes or files via `open()`
- `[camera_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[camera_bkgd.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[camera_bkgd.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[camera_bkgd.c:printf]` - Writes formatted output to standard output via `printf()`
- `[camera_fileutil.c:/mnt/sd0]` - Opens or interacts with VFS/device path `/mnt/sd0`
- `[camera_fileutil.c:/mnt/spif]` - Opens or interacts with VFS/device path `/mnt/spif`
- `[camera_fileutil.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[camera_fileutil.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
