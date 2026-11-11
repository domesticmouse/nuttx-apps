# `system/nxcodec`

## Overview
Provides NxCodec test application (`system/nxcodec`). This application is a command-line tool that verifies the functionality of NuttX codecs. Specifically, it serves as a verification tool for v4l2m2m.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_NXCODEC_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_NXCODEC]
- [Kconfig:CONFIG_SYSTEM_NXCODEC_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_NXCODEC_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_NXCODEC_STACKSIZE]
- [nxcodec.h:struct nxcodec_s]
- [nxcodec.h:nxcodec_t]
- [nxcodec.h:nxcodec_init]
- [nxcodec.h:nxcodec_start]
- [nxcodec.h:nxcodec_stop]
- [nxcodec.h:nxcodec_uninit]
- [nxcodec_context.h:struct nxcodec_context_buf_s]
- [nxcodec_context.h:struct nxcodec_context_s]
- [nxcodec_context.h:nxcodec_context_buf_t]
- [nxcodec_context.h:nxcodec_context_t]
- [nxcodec_context.h:nxcodec_context_init]
- [nxcodec_context.h:nxcodec_context_set_status]
- [nxcodec_context.h:nxcodec_context_enqueue_frame]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXCODEC]: Build and feature compilation gated by `CONFIG_SYSTEM_NXCODEC`.
- [Kconfig:CONFIG_SYSTEM_NXCODEC_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_NXCODEC_PROGNAME`.

## Side Effects
- [nxcodec.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [nxcodec.c:open]: Performs VFS file or device descriptor I/O operations.
- [nxcodec.c:printf]: Writes formatted diagnostic, logging, or console output.
- [nxcodec_context.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [nxcodec_context.c:write]: Performs VFS file or device descriptor I/O operations.
- [nxcodec_context.c:calloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
