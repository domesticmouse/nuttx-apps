# `netutils/webserver`

## Overview
Provides uIP web server (`netutils/webserver`). Enable support for the uIP web server. This tiny web server was from uIP 1.0, but has undergone many changes. It is, however,

## Interface
- [Kconfig:CONFIG_NETUTILS_WEBSERVER]
- [Kconfig:CONFIG_NETUTILS_HTTPD_SINGLECONNECT]
- [Kconfig:CONFIG_NETUTILS_HTTPD_SCRIPT_DISABLE]
- [Kconfig:CONFIG_NETUTILS_HTTPD_ENABLE_CHUNKED_ENCODING]
- [httpd.h:httpd_sendfile_open]
- [httpd.h:httpd_sendfile_close]
- [httpd.h:httpd_sendfile_send]
- [httpd.h:httpd_mmap_open]
- [httpd.h:httpd_mmap_close]
- [httpd.h:httpd_fs_open]
- [httpd.h:httpd_fs_init]
- [httpd_cgi.h:httpd_cgi]
- [httpd.c:state]
- [httpd.c:httpd_init]
- [httpd.c:httpd_listen]
- [httpd.c:httpd_send_datachunk]
- [httpd.c:httpd_send_headers]
- [httpd_cgi.c:httpd_cgi_register]

## Invariants
- [Kconfig:CONFIG_NETUTILS_WEBSERVER]: Build and feature compilation gated by `CONFIG_NETUTILS_WEBSERVER`.
- [Kconfig:CONFIG_NETUTILS_HTTPD_SINGLECONNECT]: Build and feature compilation gated by `CONFIG_NETUTILS_HTTPD_SINGLECONNECT`.
- [Kconfig:depends on NET_TCP]: Requires Kconfig dependency condition `NET_TCP`.
- [Kconfig:depends on NET_SOCKOPTS]: Requires Kconfig dependency condition `NET_SOCKOPTS`.
- [Kconfig:depends on NETUTILS_HTTPD_MMAP || NETUTILS_HTTPD_SENDFILE]: Requires Kconfig dependency condition `NETUTILS_HTTPD_MMAP || NETUTILS_HTTPD_SENDFILE`.
- [httpd.h:CONFIG_NETUTILS_HTTPD_SENDFILE]: Conditional compilation gated by `CONFIG_NETUTILS_HTTPD_SENDFILE`.

## Side Effects
- [httpd.c:close]: Performs VFS file or device descriptor I/O operations.
- [httpd.c:send]: Performs network socket creation, binding, or protocol I/O.
- [httpd.c:malloc]: Allocates or releases dynamic heap memory.
- [httpd_dirlist.c:open]: Performs VFS file or device descriptor I/O operations.
- [httpd_dirlist.c:send]: Performs network socket creation, binding, or protocol I/O.
- [httpd_dirlist.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
