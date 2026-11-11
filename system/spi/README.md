# `system/spi`

## Overview
Provides SPI tool (`system/spi`). Enable support for the SPI tool.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SPITOOL_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_SPITOOL]
- [Kconfig:CONFIG_SPITOOL_PROGNAME]
- [Kconfig:CONFIG_SPITOOL_PRIORITY]
- [Kconfig:CONFIG_SPITOOL_STACKSIZE]
- [spitool.h:struct spitool_s]
- [spitool.h:struct cmdmap_s]
- [spitool.h:spitool_exchange]
- [spitool.h:spitool_printf]
- [spitool.h:spitool_flush]
- [spitool.h:spicmd_bus]
- [spitool.h:spicmd_exch]
- [spitool.h:spitool_common_args]
- [spitool.h:spidev_path]
- [spitool.h:spidev_exists]
- [spitool.h:spidev_open]
- [spitool.h:spidev_transfer]
- [spi_bus.c:spicmd_bus]

## Invariants
- [Kconfig:CONFIG_SYSTEM_SPITOOL]: Build and feature compilation gated by `CONFIG_SYSTEM_SPITOOL`.
- [Kconfig:CONFIG_SPITOOL_PROGNAME]: Build and feature compilation gated by `CONFIG_SPITOOL_PROGNAME`.
- [Kconfig:depends on SPI]: Requires Kconfig dependency condition `SPI`.
- [Kconfig:depends on SPI_CMDDATA]: Requires Kconfig dependency condition `SPI_CMDDATA`.
- [spitool.h:CONFIG_SPITOOL_MINBUS]: Conditional compilation gated by `CONFIG_SPITOOL_MINBUS`.
- [spitool.h:CONFIG_SPITOOL_MAXBUS]: Conditional compilation gated by `CONFIG_SPITOOL_MAXBUS`.

## Side Effects
- [spi_devif.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [spi_devif.c:open]: Performs VFS file or device descriptor I/O operations.
- [spi_exch.c:close]: Performs VFS file or device descriptor I/O operations.
- [spi_exch.c:malloc]: Allocates or releases dynamic heap memory.
- [spi_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [spi_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
