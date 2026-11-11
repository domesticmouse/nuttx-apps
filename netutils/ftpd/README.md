# `netutils/ftpd`

## Overview
Provides FTP server (`netutils/ftpd`). Enable support for the FTP server.

## Interface
- [Kconfig:CONFIG_NETUTILS_FTPD]
- [Kconfig:CONFIG_FTPD_WORKERSTACKSIZE]
- [Kconfig:CONFIG_FTPD_LOGIN_PASSWD]
- [ftpd.h:enum ftpd_sessiontype_e]
- [ftpd.h:struct ftpd_pathnode_s]
- [ftpd.h:union ftpd_sockaddr_u]
- [ftpd.h:struct ftpd_account_s]
- [ftpd.h:struct ftpd_server_s]
- [ftpd.h:struct ftpd_stream_s]
- [ftpd.h:struct ftpd_session_s]
- [ftpd.h:struct ftpd_cmd_s]
- [ftpd.h:struct ftpd_protocol_s]
- [ftpd.h:FTPD_SESSIONFLAG_USER]
- [ftpd.h:FTPD_SESSIONFLAG_RESTARTPOS]
- [ftpd.h:FTPD_SESSIONFLAG_RENAMEFROM]
- [ftpd.h:FTPD_LISTOPTION_A]
- [ftpd.c:ftpd_open]
- [ftpd.c:ftpd_adduser]

## Invariants
- [Kconfig:CONFIG_NETUTILS_FTPD]: Build and feature compilation gated by `CONFIG_NETUTILS_FTPD`.
- [Kconfig:CONFIG_FTPD_WORKERSTACKSIZE]: Build and feature compilation gated by `CONFIG_FTPD_WORKERSTACKSIZE`.
- [Kconfig:depends on NET_TCP]: Requires Kconfig dependency condition `NET_TCP`.
- [Kconfig:depends on FSUTILS_PASSWD]: Requires Kconfig dependency condition `FSUTILS_PASSWD`.
- [ftpd.c:DEBUGASSERT]: Enforces `DEBUGASSERT(account)` precondition.
- [ftpd.c:DEBUGASSERT]: Enforces `DEBUGASSERT(server && account)` precondition.

## Side Effects
- [ftpd.c:close]: Performs VFS file or device descriptor I/O operations.
- [ftpd.c:accept]: Performs network socket creation, binding, or protocol I/O.
- [ftpd.c:zalloc]: Allocates or releases dynamic heap memory.
- [ftpd.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
