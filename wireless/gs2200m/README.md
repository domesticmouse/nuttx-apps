# `wireless/gs2200m`

## Overview
Provides Telit GS2200M usrsock daemon (`wireless/gs2200m`). Enable support for the gs2200m usrsock daemon

## Interface
- [Makefile:PROGNAME=$(CONFIG_WIRELESS_GS2200M_PROGNAME)]
- [Kconfig:CONFIG_WIRELESS_GS2200M]
- [Kconfig:CONFIG_WIRELESS_GS2200M_PROGNAME]
- [Kconfig:CONFIG_WIRELESS_GS2200M_PRIORITY]
- [Kconfig:CONFIG_WIRELESS_GS2200M_STACKSIZE]
- [gs2200m_main.c:enum sock_state_e]
- [gs2200m_main.c:struct usock_s]
- [gs2200m_main.c:struct gs2200m_s]
- [gs2200m_main.c:union usrsock_request_u]
- [gs2200m_main.c:main]

## Invariants
- [Kconfig:CONFIG_WIRELESS_GS2200M]: Build and feature compilation gated by `CONFIG_WIRELESS_GS2200M`.
- [Kconfig:CONFIG_WIRELESS_GS2200M_PROGNAME]: Build and feature compilation gated by `CONFIG_WIRELESS_GS2200M_PROGNAME`.
- [Kconfig:depends on NET_USRSOCK && WL_GS2200M]: Requires Kconfig dependency condition `NET_USRSOCK && WL_GS2200M`.
- [gs2200m_main.c:ASSERT]: Enforces `ASSERT(false)` precondition.
- [gs2200m_main.c:assert]: Enforces `assert(handlers[com_hdr->reqid].hdrlen <= sizeof(req))` precondition.
- [gs2200m_main.c:ASSERT]: Enforces `ASSERT(0 < usockid)` precondition.

## Side Effects
- [gs2200m_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [gs2200m_main.c:write]: Performs VFS file or device descriptor I/O operations.
- [gs2200m_main.c:calloc]: Allocates or releases dynamic heap memory.
- [gs2200m_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
