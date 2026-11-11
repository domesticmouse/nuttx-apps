# `system/vncviewer`

## Overview
Provides VNC Viewer (`system/vncviewer`). Enable the VNC Viewer example application. Connects to a VNC server and displays the remote

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_VNCVIEWER_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_VNCVIEWER]
- [Kconfig:CONFIG_SYSTEM_VNCVIEWER_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_VNCVIEWER_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_VNCVIEWER_STACKSIZE]
- [lcd_render.h:struct lcd_ctx_s]
- [lcd_render.h:lcd_init]
- [lcd_render.h:lcd_put_row]
- [lcd_render.h:lcd_fill]
- [lcd_render.h:lcd_uninit]
- [rfb_protocol.h:struct rfb_pixel_format_s]
- [rfb_protocol.h:struct rfb_server_init_s]
- [rfb_protocol.h:struct rfb_rect_hdr_s]
- [rfb_protocol.h:struct rfb_conn_s]
- [rfb_protocol.h:rfb_connect]
- [rfb_protocol.h:rfb_handshake]
- [rfb_protocol.h:rfb_set_pixel_format]
- [rfb_protocol.h:rfb_set_encodings]

## Invariants
- [Kconfig:CONFIG_SYSTEM_VNCVIEWER]: Build and feature compilation gated by `CONFIG_SYSTEM_VNCVIEWER`.
- [Kconfig:CONFIG_SYSTEM_VNCVIEWER_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_VNCVIEWER_PROGNAME`.
- [Kconfig:depends on NET_TCP && LCD]: Requires Kconfig dependency condition `NET_TCP && LCD`.

## Side Effects
- [lcd_render.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [lcd_render.c:open]: Performs VFS file or device descriptor I/O operations.
- [lcd_render.c:malloc]: Allocates or releases dynamic heap memory.
- [lcd_render.c:printf]: Writes formatted diagnostic, logging, or console output.
- [rfb_protocol.c:close]: Performs VFS file or device descriptor I/O operations.
- [rfb_protocol.c:recv]: Performs network socket creation, binding, or protocol I/O.

## Verification
- Run: `make test`
