# `netutils/dropbear`

## Overview
Provides Dropbear SSH server (`netutils/dropbear`). Enable a minimal Dropbear SSH server port for NuttX. This initial port is based on the ESP-IDF MCU test port and provides a single

## Interface
- [Makefile:PROGNAME=$(CONFIG_NETUTILS_DROPBEAR_PROGNAME)]
- [Makefile:PROGNAME=scp]
- [Kconfig:CONFIG_NETUTILS_DROPBEAR]
- [Kconfig:CONFIG_NETUTILS_DROPBEAR_STACKSIZE]
- [Kconfig:CONFIG_NETUTILS_DROPBEAR_PRIORITY]
- [Kconfig:CONFIG_NETUTILS_DROPBEAR_SHELL_PRIORITY]
- [dropbear_main.c:ATTRIB_NORETURN]
- [dropbear_main.c:main]
- [dropbear_nshsession.c:struct dropbear_nshsession_s]
- [dropbear_nshsession.c:svr_chansessinitialise]
- [dropbear_nshsession.c:svr_chansess_checksignal]
- `port`: [./port/README.md](./port/README.md) - Implements `netutils/dropbear/port` source and header components (`config.h`, `dropbear_chachapoly.c`, `dropbear_ltc_hmac_sha256.c`, `dropbear_utils.c` and 6 more files) in the NuttX application tree.

## Invariants
- [Kconfig:CONFIG_NETUTILS_DROPBEAR]: Build and feature compilation gated by `CONFIG_NETUTILS_DROPBEAR`.
- [Kconfig:CONFIG_NETUTILS_DROPBEAR_STACKSIZE]: Build and feature compilation gated by `CONFIG_NETUTILS_DROPBEAR_STACKSIZE`.
- [Kconfig:depends on NET && NET_TCP]: Requires Kconfig dependency condition `NET && NET_TCP`.
- [Kconfig:depends on !DISABLE_PSEUDOFS_OPERATIONS]: Requires Kconfig dependency condition `!DISABLE_PSEUDOFS_OPERATIONS`.
- [Kconfig:depends on !DISABLE_PTHREAD]: Requires Kconfig dependency condition `!DISABLE_PTHREAD`.
- [dropbear_main.c:CONFIG_NETUTILS_DROPBEAR_GENERATE_HOSTKEY]: Conditional compilation gated by `CONFIG_NETUTILS_DROPBEAR_GENERATE_HOSTKEY`.

## Side Effects
- [dropbear_main.c:close]: Performs VFS file or device descriptor I/O operations.
- [dropbear_main.c:accept]: Performs network socket creation, binding, or protocol I/O.
- [dropbear_main.c:printf]: Writes formatted diagnostic, logging, or console output.
- [dropbear_nshsession.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [dropbear_nshsession.c:write]: Performs VFS file or device descriptor I/O operations.
- [dropbear_nshsession.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
