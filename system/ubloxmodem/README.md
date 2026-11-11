# `system/ubloxmodem`

## Overview
Provides u-blox modem configuration tool (`system/ubloxmodem`). Enable the u-blox modem configuration tool.

## Interface
- [Makefile:PROGNAME=ubloxmodem]
- [Kconfig:CONFIG_SYSTEM_UBLOXMODEM]
- [Kconfig:CONFIG_SYSTEM_UBLOXMODEM_TTY_DEVNODE]
- [Kconfig:CONFIG_SYSTEM_UBLOXMODEM_DEVNODE]
- [ubloxmodem.h:enum ubloxmodem_cmd]
- [ubloxmodem.h:struct ubloxmodem_cxt]
- [ubloxmodem.h:struct cmdinfo]
- [ubloxmodem_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_UBLOXMODEM]: Build and feature compilation gated by `CONFIG_SYSTEM_UBLOXMODEM`.
- [Kconfig:CONFIG_SYSTEM_UBLOXMODEM_TTY_DEVNODE]: Build and feature compilation gated by `CONFIG_SYSTEM_UBLOXMODEM_TTY_DEVNODE`.
- [ubloxmodem_main.c:CONFIG_MODEM_U_BLOX_DEBUG]: Conditional compilation gated by `CONFIG_MODEM_U_BLOX_DEBUG`.
- [ubloxmodem_main.c:CONFIG_SYSTEM_UBLOXMODEM_TTY_DEVNODE]: Conditional compilation gated by `CONFIG_SYSTEM_UBLOXMODEM_TTY_DEVNODE`.

## Side Effects
- [ubloxmodem_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [ubloxmodem_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [ubloxmodem_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
