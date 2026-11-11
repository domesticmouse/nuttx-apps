# `netutils/libcurl4nx`

## Overview
Provides cURL4nx HTTP client library (`netutils/libcurl4nx`). Enable the NuttX cURL like library.

## Interface
- [Kconfig:CONFIG_NETUTILS_LIBCURL4NX]
- [Kconfig:CONFIG_LIBCURL4NX_MAXHOST]
- [Kconfig:CONFIG_LIBCURL4NX_MAXPATH]
- [Kconfig:CONFIG_LIBCURL4NX_MAXMETHOD]
- [curl4nx_private.h:struct curl4nx_header_s]
- [curl4nx_private.h:struct curl4nx_s]
- [curl4nx_private.h:CONFIG_LIBCURL4NX_MAXHOST]
- [curl4nx_private.h:CONFIG_LIBCURL4NX_MAXPATH]
- [curl4nx_private.h:CONFIG_LIBCURL4NX_MAXMETHOD]
- [curl4nx_private.h:CONFIG_LIBCURL4NX_MAXUSERAGENT]
- [curl4nx_private.h:CONFIG_LIBCURL4NX_RXBUFLEN]
- [curl4nx_private.h:CONFIG_LIBCURL4NX_MAXHEADERLINE]
- [curl4nx_private.h:CONFIG_LIBCURL4NX_MAXREDIRS]
- [curl4nx_private.h:CURL4NX_FLAGS_FAILONERROR]
- [curl4nx_private.h:CURL4NX_FLAGS_FOLLOWLOCATION]
- [curl4nx_private.h:CURL4NX_FLAGS_VERBOSE]
- [curl4nx_easy_cleanup.c:curl4nx_easy_cleanup]
- [curl4nx_easy_duphandle.c:curl4nx_easy_duphandle]

## Invariants
- [Kconfig:CONFIG_NETUTILS_LIBCURL4NX]: Build and feature compilation gated by `CONFIG_NETUTILS_LIBCURL4NX`.
- [Kconfig:CONFIG_LIBCURL4NX_MAXHOST]: Build and feature compilation gated by `CONFIG_LIBCURL4NX_MAXHOST`.
- [Kconfig:depends on NET_TCP]: Requires Kconfig dependency condition `NET_TCP`.
- [curl4nx_private.h:CONFIG_LIBCURL4NX_MAXHOST]: Conditional compilation gated by `CONFIG_LIBCURL4NX_MAXHOST`.
- [curl4nx_private.h:CONFIG_LIBCURL4NX_MAXPATH]: Conditional compilation gated by `CONFIG_LIBCURL4NX_MAXPATH`.
- [curl4nx_private.h:CONFIG_LIBCURL4NX_MAXMETHOD]: Conditional compilation gated by `CONFIG_LIBCURL4NX_MAXMETHOD`.

## Side Effects
- [curl4nx_easy_cleanup.c:free]: Allocates or releases dynamic heap memory.
- [curl4nx_easy_init.c:malloc]: Allocates or releases dynamic heap memory.
- [curl4nx_easy_perform.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [curl4nx_easy_perform.c:malloc]: Allocates or releases dynamic heap memory.
- [curl4nx_easy_perform.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [curl4nx_easy_reset.c:fwrite]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
