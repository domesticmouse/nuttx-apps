# `graphics/input/getevent`

## Overview
Implements `graphics/input/getevent` source and header components (`getevent.c`) in the NuttX application tree.

## Interface
- [getevent.c:struct touch_priv_s]
- [getevent.c:struct input_device_s]
- [getevent.c:struct input_devices_ctx_s]
- [getevent.c:main]

## Invariants
- [getevent.c:CONFIG_INPUT_MOUSE_WHEEL]: Conditional compilation gated by `CONFIG_INPUT_MOUSE_WHEEL`.
- [getevent.c:CONFIG_GRAPHICS_INPUT_GETEVENT_DETAIL_INFO]: Conditional compilation gated by `CONFIG_GRAPHICS_INPUT_GETEVENT_DETAIL_INFO`.

## Side Effects
- [getevent.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [getevent.c:open]: Performs VFS file or device descriptor I/O operations.
- [getevent.c:calloc]: Allocates or releases dynamic heap memory.
- [getevent.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
