# `netutils/ptpd`

## Overview
Provides PTPD client/server (`netutils/ptpd`). Build a minimal implementation of IEEE-1588 precision time protocol. Uses system gettimeofday() and adjtime() calls to synchronize clock

## Interface
- [Kconfig:CONFIG_NETUTILS_PTPD]
- [Kconfig:CONFIG_NETUTILS_PTPD_STACKSIZE]
- [Kconfig:CONFIG_NETUTILS_PTPD_SERVERPRIO]
- [Kconfig:CONFIG_NETUTILS_PTPD_DOMAIN]
- [ptpv2.h:end_packed_struct]
- [ptpv2.h:PTP_UDP_PORT_EVENT]
- [ptpv2.h:PTP_UDP_PORT_INFO]
- [ptpv2.h:PTP_MULTICAST_ADDR]
- [ptpv2.h:PTP_PDELAY_MULTICAST_ADDR]
- [ptpv2.h:PTP_MULTICAST_MAC]
- [ptpv2.h:PTP_PDELAY_MULTICAST_MAC]
- [ptpv2.h:ETHERTYPE_PTP]
- [ptpv2.h:PTP_MSGTYPE_MASK]
- [ptpv2.h:PTP_MSGTYPE_SYNC]
- [ptpv2.h:PTP_MSGTYPE_DELAY_REQ]
- [ptpv2.h:PTP_MSGTYPE_PDELAY_REQ]
- [ptpd.c:struct ptpd_statusreq_s]
- [ptpd.c:struct ptp_state_s]

## Invariants
- [Kconfig:CONFIG_NETUTILS_PTPD]: Build and feature compilation gated by `CONFIG_NETUTILS_PTPD`.
- [Kconfig:CONFIG_NETUTILS_PTPD_STACKSIZE]: Build and feature compilation gated by `CONFIG_NETUTILS_PTPD_STACKSIZE`.
- [Kconfig:depends on NET_IPv4]: Requires Kconfig dependency condition `NET_IPv4`.
- [Kconfig:depends on NET_IGMP]: Requires Kconfig dependency condition `NET_IGMP`.
- [Kconfig:depends on NET_UDP || NET_PKT]: Requires Kconfig dependency condition `NET_UDP || NET_PKT`.
- [ptpd.c:DEBUGASSERT]: Enforces `DEBUGASSERT(sizeof(struct ptp_announce_s) >= buflen)` precondition.

## Side Effects
- [ptpd.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [ptpd.c:open]: Performs VFS file or device descriptor I/O operations.
- [ptpd.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [ptpd.c:calloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
