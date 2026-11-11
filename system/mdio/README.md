# `system/mdio`

## Overview
Provides PHY Tool (`system/mdio`). Enable the PHY MDIO tool

## Interface
- [Makefile:PROGNAME=mdio]
- [Kconfig:CONFIG_SYSTEM_MDIO]
- [mdio_main.c:initialize_socket]
- [mdio_main.c:get_phy_id]
- [mdio_main.c:get_phy_reg]
- [mdio_main.c:set_phy_reg]
- [mdio_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_MDIO]: Build and feature compilation gated by `CONFIG_SYSTEM_MDIO`.
- [Kconfig:depends on NETDEV_PHY_IOCTL]: Requires Kconfig dependency condition `NETDEV_PHY_IOCTL`.

## Side Effects
- [mdio_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [mdio_main.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [mdio_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
