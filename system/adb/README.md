# `system/adb`

## Overview
Provides ADB daemon application (`system/adb`). Enable support for adb daemon.

## Interface
- [Makefile:PROGNAME=$(CONFIG_ADBD_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_ADBD]
- [Kconfig:CONFIG_ADBD_PROGNAME]
- [Kconfig:CONFIG_ADBD_STACKSIZE]
- [Kconfig:CONFIG_ADBD_PRIORITY]
- [adb_banner.c:adb_fill_connect_data]
- [adb_main.c:adb_log_impl]
- [adb_main.c:adb_reboot_impl]
- [adb_main.c:main]
- [logcat_service.c:struct logcat_service_s]
- [logcat_service.c:logcat_service_t]
- [logcat_service.c:logcat_service]

## Invariants
- [Kconfig:CONFIG_SYSTEM_ADBD]: Build and feature compilation gated by `CONFIG_SYSTEM_ADBD`.
- [Kconfig:CONFIG_ADBD_PROGNAME]: Build and feature compilation gated by `CONFIG_ADBD_PROGNAME`.
- [Kconfig:depends on LIBUV]: Requires Kconfig dependency condition `LIBUV`.
- [Kconfig:depends on !BOARDCTL_UNIQUEID]: Requires Kconfig dependency condition `!BOARDCTL_UNIQUEID`.
- [Kconfig:depends on NET_TCP_NO_STACK || NET_TCPBACKLOG]: Requires Kconfig dependency condition `NET_TCP_NO_STACK || NET_TCPBACKLOG`.
- [adb_banner.c:CONFIG_BOARDCTL_UNIQUEID]: Conditional compilation gated by `CONFIG_BOARDCTL_UNIQUEID`.

## Side Effects
- [adb_main.c:syslog]: Writes formatted diagnostic, logging, or console output.
- [logcat_service.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [logcat_service.c:close]: Performs VFS file or device descriptor I/O operations.
- [logcat_service.c:free]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
