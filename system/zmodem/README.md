# `system/zmodem`

## Overview
Provides Zmodem Commands (`system/zmodem`). This selection enables the 'sz' and 'rz' NSH commands.

## Interface
- [Makefile:PROGNAME=sz]
- [Kconfig:CONFIG_SYSTEM_ZMODEM]
- [Kconfig:CONFIG_SYSTEM_ZMODEM_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_ZMODEM_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_ZMODEM_DEVNAME]
- [zm.h:enum parser_state_e]
- [zm.h:enum pidle_substate_e]
- [zm.h:enum pheader_substate_e]
- [zm.h:enum pdata_substate_e]
- [zm.h:struct zm_transition_s]
- [zm.h:struct zm_state_s]
- [zm.h:struct zmr_state_s]
- [zm.h:struct zms_state_s]
- [zm.h:zm_bytobe32]
- [zm.h:zm_be32toby]
- [zm.h:zm_encnibble]
- [zm.h:zm_decnibble]
- [zm.h:zm_puthex8]
- `host`: [./host/README.md](./host/README.md) - Implements `system/zmodem/host` source and header components (`crc16.c`, `crc32.c`, `debug.h`) in the NuttX application tree.

## Invariants
- [Kconfig:CONFIG_SYSTEM_ZMODEM]: Build and feature compilation gated by `CONFIG_SYSTEM_ZMODEM`.
- [Kconfig:CONFIG_SYSTEM_ZMODEM_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_ZMODEM_PRIORITY`.
- [Kconfig:depends on SERIAL_TERMIOS]: Requires Kconfig dependency condition `SERIAL_TERMIOS`.
- [Kconfig:depends on RTC]: Requires Kconfig dependency condition `RTC`.
- [Kconfig:depends on DEBUG_ZMODEM]: Requires Kconfig dependency condition `DEBUG_ZMODEM`.
- [zm.h:CONFIG_DEBUG_ZMODEM]: Conditional compilation gated by `CONFIG_DEBUG_ZMODEM`.

## Side Effects
- [zm.h:syslog]: Writes formatted diagnostic, logging, or console output.
- [rz_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [rz_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [sz_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [sz_main.c:free]: Allocates or releases dynamic heap memory.
- [sz_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
