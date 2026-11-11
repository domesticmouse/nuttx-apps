# `netutils/thttpd`

## Overview
Provides THTTPD webserver (`netutils/thttpd`). Enable support for the THTTPD webservert.

## Interface
- [Makefile:PROGNAME=phf]
- [Kconfig:CONFIG_NETUTILS_THTTPD]
- [Kconfig:CONFIG_THTTPD_NFILE_DESCRIPTORS]
- [Kconfig:CONFIG_THTTPD_PORT]
- [Kconfig:CONFIG_THTTPD_IPADDR]
- [config.h:CONFIG_THTTPD]
- [config.h:CONFIG_THTTPD_PORT]
- [config.h:CONFIG_THTTPD_IPADDR]
- [config.h:CONFIG_THTTPD_SERVER_ADDRESS]
- [config.h:CONFIG_THTTPD_SERVER_SOFTWARE]
- [config.h:CONFIG_THTTPD_PATH]
- [config.h:CONFIG_THTTPD_CGI_PATH]
- [config.h:CONFIG_THTTPD_CGI_PATTERN]
- [config.h:CONFIG_THTTPD_CGI_PRIORITY]
- [config.h:CONFIG_THTTPD_CGI_STACKSIZE]
- [config.h:CONFIG_THTTPD_CGI_BYTECOUNT]
- [fdwatch.h:struct fdwatch_s]
- [fdwatch.h:fdwatch_initialize]
- `cgi-src`: [./cgi-src/README.md](./cgi-src/README.md) - Implements `netutils/thttpd/cgi-src` source and header components (`phf.c`, `redirect.c`, `ssi.c`) in the NuttX application tree.

## Invariants
- [Kconfig:CONFIG_NETUTILS_THTTPD]: Build and feature compilation gated by `CONFIG_NETUTILS_THTTPD`.
- [Kconfig:CONFIG_THTTPD_NFILE_DESCRIPTORS]: Build and feature compilation gated by `CONFIG_THTTPD_NFILE_DESCRIPTORS`.
- [Kconfig:depends on NXFLAT || FS_BINFS]: Requires Kconfig dependency condition `NXFLAT || FS_BINFS`.
- [Kconfig:depends on NXFLAT]: Requires Kconfig dependency condition `NXFLAT`.
- [Kconfig:depends on FS_BINFS]: Requires Kconfig dependency condition `FS_BINFS`.
- [config.h:CONFIG_NET]: Conditional compilation gated by `CONFIG_NET`.

## Side Effects
- [thttpd_alloc.h:malloc]: Allocates or releases dynamic heap memory.
- [fdwatch.c:zalloc]: Allocates or releases dynamic heap memory.
- [libhttpd.c:close]: Performs VFS file or device descriptor I/O operations.
- [libhttpd.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [libhttpd.c:zalloc]: Allocates or releases dynamic heap memory.
- [libhttpd.c:task_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
