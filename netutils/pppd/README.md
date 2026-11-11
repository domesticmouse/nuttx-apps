# `netutils/pppd`

## Overview
Provides PPP server (`netutils/pppd`). Enable support for the PPP daemon.

## Interface
- [Kconfig:CONFIG_NETUTILS_PPPD]
- [Kconfig:CONFIG_NETUTILS_PPPD_PAP]
- [ahdlc.h:ahdlc_init]
- [ahdlc.h:ahdlc_rx_ready]
- [ahdlc.h:ahdlc_rx]
- [ahdlc.h:ahdlc_tx]
- [ipcp.h:struct _ipcp]
- [ipcp.h:IPCPPKT]
- [ipcp.h:ipcp_init]
- [ipcp.h:ipcp_task]
- [ipcp.h:ipcp_rx]
- [ipcp.h:IPCP_IPADDRESS]
- [ipcp.h:IPCP_PRIMARY_DNS]
- [ipcp.h:IPCP_SECONDARY_DNS]
- [ipcp.h:IPCP_TX_UP]
- [ipcp.h:IPCP_RX_UP]
- [lcp.h:struct _lcppkt]
- [lcp.h:LCPPKT]

## Invariants
- [Kconfig:CONFIG_NETUTILS_PPPD]: Build and feature compilation gated by `CONFIG_NETUTILS_PPPD`.
- [Kconfig:CONFIG_NETUTILS_PPPD_PAP]: Build and feature compilation gated by `CONFIG_NETUTILS_PPPD_PAP`.
- [Kconfig:depends on NET && NET_UDP]: Requires Kconfig dependency condition `NET && NET_UDP`.
- [ppp.h:CONFIG_NETUTILS_PPPD_PAP]: Conditional compilation gated by `CONFIG_NETUTILS_PPPD_PAP`.
- [lcp.c:CONFIG_NETUTILS_PPPD_PAP]: Conditional compilation gated by `CONFIG_NETUTILS_PPPD_PAP`.
- [ppp.c:CONFIG_NETUTILS_PPPD_PAP]: Conditional compilation gated by `CONFIG_NETUTILS_PPPD_PAP`.

## Side Effects
- [pppd.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [pppd.c:open]: Performs VFS file or device descriptor I/O operations.
- [pppd.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
