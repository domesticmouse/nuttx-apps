# `netutils/tftpc`

## Overview
Provides TFTP client (`netutils/tftpc`). Enable support for the TFTP client.

## Interface
- [Kconfig:CONFIG_NETUTILS_TFTPC]
- [tftpc_internal.h:tftp_sockinit]
- [tftpc_internal.h:tftp_mkreqpacket]
- [tftpc_internal.h:tftp_mkackpacket]
- [tftpc_internal.h:tftp_mkerrpacket]
- [tftpc_internal.h:tftp_parseerrpacket]
- [tftpc_internal.h:tftp_recvfrom]
- [tftpc_internal.h:tftp_sendto]
- [tftpc_internal.h:CONFIG_NETUTILS_TFTP_PORT]
- [tftpc_internal.h:CONFIG_NETUTILS_TFTP_TIMEOUT]
- [tftpc_internal.h:TFTP_ACKHEADERSIZE]
- [tftpc_internal.h:TFTP_ERRHEADERSIZE]
- [tftpc_internal.h:TFTP_DATAHEADERSIZE]
- [tftpc_internal.h:TFTP_MAXPACKETSIZE]
- [tftpc_internal.h:TFTP_PACKETSIZE]
- [tftpc_internal.h:TFTP_DATASIZE]
- [tftpc_get.c:tftpget_cb]
- [tftpc_get.c:tftpget]

## Invariants
- [Kconfig:CONFIG_NETUTILS_TFTPC]: Build and feature compilation gated by `CONFIG_NETUTILS_TFTPC`.
- [Kconfig:depends on NET_UDP && NET_IPv4]: Requires Kconfig dependency condition `NET_UDP && NET_IPv4`.
- [tftpc_internal.h:CONFIG_NETUTILS_TFTP_PORT]: Conditional compilation gated by `CONFIG_NETUTILS_TFTP_PORT`.
- [tftpc_internal.h:CONFIG_NETUTILS_TFTP_TIMEOUT]: Conditional compilation gated by `CONFIG_NETUTILS_TFTP_TIMEOUT`.
- [tftpc_internal.h:CONFIG_NET_ETHERNET]: Conditional compilation gated by `CONFIG_NET_ETHERNET`.
- [tftpc_internal.h:CONFIG_CPP_HAVE_WARNING]: Conditional compilation gated by `CONFIG_CPP_HAVE_WARNING`.

## Side Effects
- [tftpc_get.c:close]: Performs VFS file or device descriptor I/O operations.
- [tftpc_get.c:zalloc]: Allocates or releases dynamic heap memory.
- [tftpc_packets.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [tftpc_put.c:close]: Performs VFS file or device descriptor I/O operations.
- [tftpc_put.c:zalloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
