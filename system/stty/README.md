# `system/stty`

## Overview
Provides stty - set terminal options (`system/stty`). Enable the stty command to configure terminal (TTY) settings. This command allows you to view and change terminal attributes

## Interface
- [Makefile:PROGNAME=stty]
- [Kconfig:CONFIG_SYSTEM_STTY]
- [Kconfig:CONFIG_SYSTEM_STTY_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_STTY_STACKSIZE]
- [stty_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_STTY]: Build and feature compilation gated by `CONFIG_SYSTEM_STTY`.
- [Kconfig:CONFIG_SYSTEM_STTY_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_STTY_PRIORITY`.
- [Kconfig:depends on SERIAL_TERMIOS]: Requires Kconfig dependency condition `SERIAL_TERMIOS`.

## Side Effects
- [stty_main.c:read]: Performs VFS file or device descriptor I/O operations.
- [stty_main.c:dprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
