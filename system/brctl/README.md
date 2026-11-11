# `system/brctl`

## Overview
Provides Ethernet bridge 'brctl' command (`system/brctl`). Enable the 'brctl' command to create Ethernet bridges and to add or remove their ports.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_BRCTL_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_BRCTL]
- [Kconfig:CONFIG_SYSTEM_BRCTL_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_BRCTL_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_BRCTL_STACKSIZE]
- [brctl.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_BRCTL]: Build and feature compilation gated by `CONFIG_SYSTEM_BRCTL`.
- [Kconfig:CONFIG_SYSTEM_BRCTL_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_BRCTL_PROGNAME`.
- [Kconfig:depends on NET_BRIDGE]: Requires Kconfig dependency condition `NET_BRIDGE`.

## Side Effects
- [brctl.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
