# `system/dhcpc`

## Overview
Provides DHCP Address Renewal (`system/dhcpc`). Enable the DHCP client 'renew' command

## Interface
- [Makefile:PROGNAME=$(CONFIG_DHCPC_RENEW_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_DHCPC_RENEW]
- [Kconfig:CONFIG_DHCPC_RENEW_PROGNAME]
- [Kconfig:CONFIG_DHCPC_RENEW_PRIORITY]
- [Kconfig:CONFIG_DHCPC_RENEW_STACKSIZE]
- [renew_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_DHCPC_RENEW]: Build and feature compilation gated by `CONFIG_SYSTEM_DHCPC_RENEW`.
- [Kconfig:CONFIG_DHCPC_RENEW_PROGNAME]: Build and feature compilation gated by `CONFIG_DHCPC_RENEW_PROGNAME`.
- [Kconfig:depends on NET_UDP]: Requires Kconfig dependency condition `NET_UDP`.

## Side Effects
- [renew_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
