# `graphics/tiff`

## Overview
Provides TIFF file generation library (`graphics/tiff`). Enable support for the TIFF file generation program.

## Interface
- [Kconfig:CONFIG_TIFF]
- [tiff_internal.h:tiff_read]
- [tiff_internal.h:tiff_write]
- [tiff_internal.h:tiff_putint16]
- [tiff_internal.h:tiff_putint32]
- [tiff_internal.h:tiff_putstring]
- [tiff_internal.h:tiff_wordalign]
- [tiff_internal.h:IMGFLAGS_BILEV_BIT]
- [tiff_internal.h:IMGFLAGS_GREY_BIT]
- [tiff_internal.h:IMGFLAGS_GREY8_BIT]
- [tiff_internal.h:IMGFLAGS_RGB_BIT]
- [tiff_internal.h:IMGFLAGS_RGB565_BIT]
- [tiff_internal.h:IMGFLAGS_FMT_Y1]
- [tiff_internal.h:IMGFLAGS_FMT_Y4]
- [tiff_internal.h:IMGFLAGS_FMT_Y8]
- [tiff_internal.h:IMGFLAGS_FMT_RGB16_565]
- [tiff_addstrip.c:tiff_convstrip]
- [tiff_addstrip.c:tiff_addstrip]

## Invariants
- [Kconfig:CONFIG_TIFF]: Build and feature compilation gated by `CONFIG_TIFF`.
- [tiff_addstrip.c:DEBUGASSERT]: Enforces `DEBUGASSERT(info->iobuffer != NULL)` precondition.
- [tiff_addstrip.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ntotal == info->bps)` precondition.
- [tiff_addstrip.c:CONFIG_DEBUG_GRAPHICS]: Conditional compilation gated by `CONFIG_DEBUG_GRAPHICS`.
- [tiff_finalize.c:DEBUGASSERT]: Enforces `DEBUGASSERT((info->outsize & 3) == 0 && (info->tmp1size & 3) == 0)` precondition.
- [tiff_finalize.c:DEBUGASSERT]: Enforces `DEBUGASSERT(total == info->tmp1size)` precondition.

## Side Effects
- [tiff_finalize.c:close]: Performs VFS file or device descriptor I/O operations.
- [tiff_initialize.c:open]: Performs VFS file or device descriptor I/O operations.
- [tiff_utils.c:read]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
