# `netutils/wifibridge`

## Overview
Provides Wi-Fi SoftAP to Ethernet bridge (`netutils/wifibridge`). Library that turns a Wi-Fi interface into a SoftAP and bridges it to an Ethernet interface at layer 2, so that Ethernet devices

## Interface
- [Kconfig:CONFIG_NETUTILS_WIFIBRIDGE]
- [Kconfig:CONFIG_NETUTILS_WIFIBRIDGE_DHCPD]
- [Kconfig:CONFIG_NETUTILS_WIFIBRIDGE_PERSIST]
- [Kconfig:CONFIG_NETUTILS_WIFIBRIDGE_STORAGE]
- [wifibridge.c:struct wifibridge_record_s]
- [wifibridge.c:wifibridge_start]
- [wifibridge.c:wifibridge_stop]
- [wifibridge.c:wifibridge_status]
- [wifibridge.c:wifibridge_save]
- [wifibridge.c:wifibridge_load]
- [wifibridge.c:wifibridge_clear]

## Invariants
- [Kconfig:CONFIG_NETUTILS_WIFIBRIDGE]: Build and feature compilation gated by `CONFIG_NETUTILS_WIFIBRIDGE`.
- [Kconfig:CONFIG_NETUTILS_WIFIBRIDGE_DHCPD]: Build and feature compilation gated by `CONFIG_NETUTILS_WIFIBRIDGE_DHCPD`.
- [Kconfig:depends on NET_IPv4 && NET_BRIDGE && WIRELESS_WAPI]: Requires Kconfig dependency condition `NET_IPv4 && NET_BRIDGE && WIRELESS_WAPI`.
- [Kconfig:depends on NETUTILS_DHCPD]: Requires Kconfig dependency condition `NETUTILS_DHCPD`.
- [wifibridge.c:CONFIG_NETUTILS_WIFIBRIDGE_DHCPD]: Conditional compilation gated by `CONFIG_NETUTILS_WIFIBRIDGE_DHCPD`.
- [wifibridge.c:CONFIG_NETUTILS_WIFIBRIDGE_PERSIST]: Conditional compilation gated by `CONFIG_NETUTILS_WIFIBRIDGE_PERSIST`.

## Side Effects
- [wifibridge.c:close]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
