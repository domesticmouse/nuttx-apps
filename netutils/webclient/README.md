# `netutils/webclient`

## Overview
Provides uIP web client (`netutils/webclient`). Enable support for the uIP web client.

## Interface
- [Kconfig:CONFIG_NETUTILS_WEBCLIENT]
- [Kconfig:CONFIG_NSH_WGET_USERAGENT]
- [Kconfig:CONFIG_WEBCLIENT_TIMEOUT]
- [Kconfig:CONFIG_WEBCLIENT_MAXHTTPLINE]
- [webclient.c:enum webclient_state_e]
- [webclient.c:struct wget_target_s]
- [webclient.c:struct wget_s]
- [webclient.c:webclient_conn_send]
- [webclient.c:webclient_conn_recv]
- [webclient.c:webclient_conn_close]
- [webclient.c:webclient_conn_free]
- [webclient.c:webclient_perform]
- [webclient.c:webclient_abort]
- [webclient.c:web_post_str]
- [webclient.c:web_post_strlen]
- [webclient.c:web_posts_str]
- [webclient.c:web_posts_strlen]
- [webclient.c:wget]

## Invariants
- [Kconfig:CONFIG_NETUTILS_WEBCLIENT]: Build and feature compilation gated by `CONFIG_NETUTILS_WEBCLIENT`.
- [Kconfig:CONFIG_NSH_WGET_USERAGENT]: Build and feature compilation gated by `CONFIG_NSH_WGET_USERAGENT`.
- [Kconfig:depends on NET_TCP]: Requires Kconfig dependency condition `NET_TCP`.
- [webclient.c:DEBUGASSERT]: Enforces `DEBUGASSERT((ctx)->state == (s))` precondition.
- [webclient.c:DEBUGASSERT]: Enforces `DEBUGASSERT(errno == ERANGE)` precondition.
- [webclient.c:DEBUGASSERT]: Enforces `DEBUGASSERT(val == UINTMAX_MAX)` precondition.

## Side Effects
- [webclient.c:close]: Performs VFS file or device descriptor I/O operations.
- [webclient.c:send]: Performs network socket creation, binding, or protocol I/O.
- [webclient.c:free]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
