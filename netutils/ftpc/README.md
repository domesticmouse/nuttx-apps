# `netutils/ftpc`

## Overview
Provides FTP client (`netutils/ftpc`). Enable support for the FTP client.

## Interface
- [Kconfig:CONFIG_NETUTILS_FTPC]
- [Kconfig:CONFIG_DEBUG_FTPC]
- [Kconfig:CONFIG_FTP_TMPDIR]
- [Kconfig:CONFIG_FTP_SIZE_CMD_MODE_BINARY]
- [ftpc_config.h:CONFIG_DEBUG_NET]
- [ftpc_config.h:CONFIG_DEBUG_NET_ERROR]
- [ftpc_config.h:CONFIG_DEBUG_NET_WARN]
- [ftpc_config.h:CONFIG_DEBUG_NET_INFO]
- [ftpc_internal.h:struct ftpc_socket_s]
- [ftpc_internal.h:struct ftpc_session_s]
- [ftpc_internal.h:ftpc_stripcrlf]
- [ftpc_internal.h:ftpc_stripslash]
- [ftpc_internal.h:ftpc_dequote]
- [ftpc_internal.h:ftpc_reconnect]
- [ftpc_internal.h:ftpc_relogin]
- [ftpc_internal.h:ftpc_reset]
- [ftpc_internal.h:ftpc_cmd]
- [ftpc_internal.h:fptc_getreply]

## Invariants
- [Kconfig:CONFIG_NETUTILS_FTPC]: Build and feature compilation gated by `CONFIG_NETUTILS_FTPC`.
- [Kconfig:CONFIG_DEBUG_FTPC]: Build and feature compilation gated by `CONFIG_DEBUG_FTPC`.
- [Kconfig:depends on DEBUG_FEATURES]: Requires Kconfig dependency condition `DEBUG_FEATURES`.
- [Kconfig:depends on NET_SENDFILE]: Requires Kconfig dependency condition `NET_SENDFILE`.
- [ftpc_config.h:CONFIG_DEBUG_NET]: Conditional compilation gated by `CONFIG_DEBUG_NET`.
- [ftpc_config.h:CONFIG_DEBUG_FTPC]: Conditional compilation gated by `CONFIG_DEBUG_FTPC`.

## Side Effects
- [ftpc_chdir.c:free]: Allocates or releases dynamic heap memory.
- [ftpc_cmd.c:free]: Allocates or releases dynamic heap memory.
- [ftpc_connect.c:zalloc]: Allocates or releases dynamic heap memory.
- [ftpc_disconnect.c:free]: Allocates or releases dynamic heap memory.
- [ftpc_getfile.c:fread]: Performs VFS file or device descriptor I/O operations.
- [ftpc_getfile.c:free]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
