# `system/kbd`

## Overview
Provides Keyboard dump (`system/kbd`). Dump what a keyboard reports. This reads any keyboard registered with keyboard_register(), whatever the hardware behind it is, so it

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_KBD_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_KBD]
- [Kconfig:CONFIG_SYSTEM_KBD_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_KBD_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_KBD_STACKSIZE]
- [kbd_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_KBD]: Build and feature compilation gated by `CONFIG_SYSTEM_KBD`.
- [Kconfig:CONFIG_SYSTEM_KBD_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_KBD_PROGNAME`.
- [Kconfig:depends on INPUT_KEYBOARD]: Requires Kconfig dependency condition `INPUT_KEYBOARD`.
- [kbd_main.c:CONFIG_INPUT_KEYBOARD_BYTESTREAM]: Conditional compilation gated by `CONFIG_INPUT_KEYBOARD_BYTESTREAM`.

## Side Effects
- [kbd_main.c:write]: Performs VFS file or device descriptor I/O operations.
- [kbd_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
