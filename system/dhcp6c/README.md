# `system/dhcp6c`

## Overview
Provides DHCP IPv6 Address Renewal (`system/dhcp6c`). Enable the DHCP client 'renew6' command

## Interface
- [Makefile:PROGNAME=$(CONFIG_DHCPC_RENEW6_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_DHCPC_RENEW6]
- [Kconfig:CONFIG_DHCPC_RENEW6_PROGNAME]
- [Kconfig:CONFIG_DHCPC_RENEW6_PRIORITY]
- [Kconfig:CONFIG_DHCPC_RENEW6_STACKSIZE]
- [renew6_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_DHCPC_RENEW6]: Build and feature compilation gated by `CONFIG_SYSTEM_DHCPC_RENEW6`.
- [Kconfig:CONFIG_DHCPC_RENEW6_PROGNAME]: Build and feature compilation gated by `CONFIG_DHCPC_RENEW6_PROGNAME`.
- [Kconfig:depends on NET_UDP && NET_IPv6 && NET_ICMPv6_AUTOCONF]: Requires Kconfig dependency condition `NET_UDP && NET_IPv6 && NET_ICMPv6_AUTOCONF`.

## Side Effects
- None

## Verification
- Run: `make test`
