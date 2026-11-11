# uvc_cam

## Overview
UVC Camera streaming example (`uvc_cam`). Captures frames from V4L2 camera and streams to USB host via UVC gadget driver (/dev/uvc0).

## Interface
- `[Kconfig:EXAMPLES_UVC_CAM]` - Build configuration option `EXAMPLES_UVC_CAM`
- `[Kconfig:EXAMPLES_UVC_CAM_PROGNAME]` - Build configuration option `EXAMPLES_UVC_CAM_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_UVC_CAM_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_UVC_CAM_PROGNAME}`
- `[uvc_cam_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on USBUVC && VIDEO]` - Requires kernel/app configuration `USBUVC && VIDEO`
- `[uvc_cam_main.c:CONFIG_EXAMPLES_UVC_CAM_NFRAMES]` - Configuration guard on `CONFIG_EXAMPLES_UVC_CAM_NFRAMES`
- `[uvc_cam_main.c:CONFIG_USBUVC_COMPOSITE]` - Configuration guard on `CONFIG_USBUVC_COMPOSITE`
- `[uvc_cam_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[uvc_cam_main.c:/dev/uvc0]` - Opens or interacts with VFS/device path `/dev/uvc0`
- `[uvc_cam_main.c:/dev/video0]` - Opens or interacts with VFS/device path `/dev/video0`
- `[uvc_cam_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[uvc_cam_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[uvc_cam_main.c:open]` - Opens device nodes or files via `open()`
- `[uvc_cam_main.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[uvc_cam_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
