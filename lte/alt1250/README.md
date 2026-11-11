# `lte/alt1250`

## Overview
Provides ALT1250 usrsock daemon (`lte/alt1250`). Enable support for the alt1250 usrsock daemon

## Interface
- [Makefile:PROGNAME=$(CONFIG_LTE_ALT1250_PROGNAME)]
- [Kconfig:CONFIG_LTE_ALT1250]
- [Kconfig:CONFIG_LTE_ALT1250_PROGNAME]
- [Kconfig:CONFIG_LTE_ALT1250_PRIORITY]
- [Kconfig:CONFIG_LTE_ALT1250_STACKSIZE]
- [alt1250_atcmd.h:struct atreply_truefalse_s]
- [alt1250_atcmd.h:atcmdreply_ok_error]
- [alt1250_atcmd.h:check_atreply_ok]
- [alt1250_atcmd.h:check_atreply_truefalse]
- [alt1250_atcmd.h:lwm2mstub_send_reset]
- [alt1250_atcmd.h:lwm2mstub_send_getenable]
- [alt1250_atcmd.h:lwm2mstub_send_setenable]
- [alt1250_atcmd.h:lwm2mstub_send_getnamemode]
- [alt1250_atcmd.h:lwm2mstub_send_setnamemode]
- [alt1250_atcmd.h:lwm2mstub_send_getversion]
- [alt1250_atcmd.h:lwm2mstub_send_setversion]
- [alt1250_atcmd.h:lwm2mstub_send_getwriteattr]
- [alt1250_atcmd.h:lwm2mstub_send_setwriteattr]
- `callback_handlers`: [./callback_handlers/README.md](./callback_handlers/README.md) - Implements `lte/alt1250/callback_handlers` source and header components (`alt1250_evt.c`, `alt1250_evt.h`) in the NuttX application tree.
- `usock_handlers`: [./usock_handlers/README.md](./usock_handlers/README.md) - Implements `lte/alt1250/usock_handlers` source and header components (`alt1250_accepthdlr.c`, `alt1250_bindhdlr.c`, `alt1250_closehdlr.c`, `alt1250_connecthdlr.c` and 24 more files) in the NuttX application tree.

## Invariants
- [Kconfig:CONFIG_LTE_ALT1250]: Build and feature compilation gated by `CONFIG_LTE_ALT1250`.
- [Kconfig:CONFIG_LTE_ALT1250_PROGNAME]: Build and feature compilation gated by `CONFIG_LTE_ALT1250_PROGNAME`.
- [Kconfig:depends on NET_USRSOCK && MODEM_ALT1250]: Requires Kconfig dependency condition `NET_USRSOCK && MODEM_ALT1250`.
- [Kconfig:depends on PM]: Requires Kconfig dependency condition `PM`.
- [Kconfig:depends on LTE_ALT1250_SMS_TOA]: Requires Kconfig dependency condition `LTE_ALT1250_SMS_TOA`.
- [alt1250_daemon.h:CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE]: Conditional compilation gated by `CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE`.

## Side Effects
- [alt1250_devif.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [alt1250_devif.c:open]: Performs VFS file or device descriptor I/O operations.
- [alt1250_main.c:calloc]: Allocates or releases dynamic heap memory.
- [alt1250_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [alt1250_usockif.c:write]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
