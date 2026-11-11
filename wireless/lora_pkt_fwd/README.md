# `wireless/lora_pkt_fwd`

## Overview
Provides LoRaWAN Semtech UDP packet forwarder (`wireless/lora_pkt_fwd`). Forwards the packets received by a LoRa concentrator to a LoRaWAN network server using the Semtech UDP protocol version 2, and turns

## Interface
- [Makefile:PROGNAME=$(CONFIG_LORA_PKT_FWD_PROGNAME)]
- [Kconfig:CONFIG_WIRELESS_LORA_PKT_FWD]
- [Kconfig:CONFIG_LORA_PKT_FWD_PROGNAME]
- [Kconfig:CONFIG_LORA_PKT_FWD_PRIORITY]
- [Kconfig:CONFIG_LORA_PKT_FWD_STACKSIZE]
- [lora_pkt_fwd.h:struct lora_fwd_config_s]
- [lora_pkt_fwd.h:struct lora_fwd_stats_s]
- [lora_pkt_fwd.h:lora_fwd_init]
- [lora_pkt_fwd.h:lora_fwd_start]
- [lora_pkt_fwd.h:lora_fwd_stop]
- [lora_pkt_fwd.h:lora_fwd_isrunning]
- [lora_pkt_fwd.h:lora_fwd_config]
- [lora_pkt_fwd.h:lora_fwd_getstats]
- [lora_pkt_fwd.h:lora_fwd_setserver]
- [lora_pkt_fwd.h:lora_fwd_parse_eui]
- [lora_main.c:main]
- [lora_pkt_fwd.c:lora_fwd_init]
- [lora_pkt_fwd.c:lora_fwd_start]

## Invariants
- [Kconfig:CONFIG_WIRELESS_LORA_PKT_FWD]: Build and feature compilation gated by `CONFIG_WIRELESS_LORA_PKT_FWD`.
- [Kconfig:CONFIG_LORA_PKT_FWD_PROGNAME]: Build and feature compilation gated by `CONFIG_LORA_PKT_FWD_PROGNAME`.
- [Kconfig:depends on LPWAN_LORA_GW && NET_UDP && NETUTILS_NETLIB]: Requires Kconfig dependency condition `LPWAN_LORA_GW && NET_UDP && NETUTILS_NETLIB`.
- [lora_main.c:CONFIG_NETUTILS_DHCPC]: Conditional compilation gated by `CONFIG_NETUTILS_DHCPC`.
- [lora_pkt_fwd.c:CONFIG_LORA_PKT_FWD_EUI_FROM_MAC]: Conditional compilation gated by `CONFIG_LORA_PKT_FWD_EUI_FROM_MAC`.

## Side Effects
- [lora_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [lora_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [lora_main.c:printf]: Writes formatted diagnostic, logging, or console output.
- [lora_pkt_fwd.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [lora_pkt_fwd.c:close]: Performs VFS file or device descriptor I/O operations.
- [lora_pkt_fwd.c:socket]: Performs network socket creation, binding, or protocol I/O.

## Verification
- Run: `make test`
