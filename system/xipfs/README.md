# `system/xipfs`

## Overview
Provides xipfs defragmentation command (`system/xipfs`). Enable the 'xipfs' command, which compacts a xipfs volume and reports how its erase blocks are laid out. With -n it only

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_XIPFS_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_XIPFS]
- [Kconfig:CONFIG_SYSTEM_XIPFS_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_XIPFS_MOUNTPOINT]
- [Kconfig:CONFIG_SYSTEM_XIPFS_PRIORITY]
- [xipfs_main.c:struct xipfs_entry_s]
- [xipfs_main.c:struct xipfs_survey_s]
- [xipfs_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_XIPFS]: Build and feature compilation gated by `CONFIG_SYSTEM_XIPFS`.
- [Kconfig:CONFIG_SYSTEM_XIPFS_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_XIPFS_PROGNAME`.
- [Kconfig:depends on FS_XIPFS]: Requires Kconfig dependency condition `FS_XIPFS`.

## Side Effects
- [xipfs_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [xipfs_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [xipfs_main.c:free]: Allocates or releases dynamic heap memory.
- [xipfs_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
