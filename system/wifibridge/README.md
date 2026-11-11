# `system/wifibridge`

## Overview
Provides Wi-Fi to Ethernet bridge 'wifibridge' command (`system/wifibridge`). Enable the 'wifibridge' command to start, stop and inspect a Wi-Fi SoftAP bridged to an Ethernet interface.

## Interface
- [Makefile:PROGNAME=wifibridge]
- [Kconfig:CONFIG_SYSTEM_WIFIBRIDGE]
- [Kconfig:CONFIG_SYSTEM_WIFIBRIDGE_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_WIFIBRIDGE_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_WIFIBRIDGE_BRIDGE]
- [wifibridge_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_WIFIBRIDGE]: Build and feature compilation gated by `CONFIG_SYSTEM_WIFIBRIDGE`.
- [Kconfig:CONFIG_SYSTEM_WIFIBRIDGE_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_WIFIBRIDGE_PRIORITY`.
- [Kconfig:depends on NET_IPv4 && NET_BRIDGE && WIRELESS_WAPI]: Requires Kconfig dependency condition `NET_IPv4 && NET_BRIDGE && WIRELESS_WAPI`.
- [wifibridge_main.c:CONFIG_NETUTILS_WIFIBRIDGE_PERSIST]: Conditional compilation gated by `CONFIG_NETUTILS_WIFIBRIDGE_PERSIST`.
- [wifibridge_main.c:CONFIG_NETUTILS_WIFIBRIDGE_DHCPD]: Conditional compilation gated by `CONFIG_NETUTILS_WIFIBRIDGE_DHCPD`.

## Side Effects
- [wifibridge_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
