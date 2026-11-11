# `system/lm75`

## Overview
Provides Temperature (`system/lm75`). Enable support for the NSH temp command. This command will read the current temperature from an LM-75 (or compatible) temperature sensor

## Interface
- [Makefile:PROGNAME=lm75]
- [Kconfig:CONFIG_SYSTEM_LM75]
- [Kconfig:CONFIG_SYSTEM_LM75_DEVNAME]
- [Kconfig:CONFIG_SYSTEM_LM75_FAHRENHEIT]
- [Kconfig:CONFIG_SYSTEM_LM75_CELSIUS]
- [lm75.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_LM75]: Build and feature compilation gated by `CONFIG_SYSTEM_LM75`.
- [Kconfig:CONFIG_SYSTEM_LM75_DEVNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_LM75_DEVNAME`.
- [Kconfig:depends on LM75_I2C]: Requires Kconfig dependency condition `LM75_I2C`.
- [lm75.c:CONFIG_SYSTEM_LM75_DEVNAME]: Conditional compilation gated by `CONFIG_SYSTEM_LM75_DEVNAME`.
- [lm75.c:CONFIG_SYSTEM_LM75_FAHRENHEIT]: Conditional compilation gated by `CONFIG_SYSTEM_LM75_FAHRENHEIT`.
- [lm75.c:CONFIG_SYSTEM_LM75_CELSIUS]: Conditional compilation gated by `CONFIG_SYSTEM_LM75_CELSIUS`.

## Side Effects
- [lm75.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [lm75.c:open]: Performs VFS file or device descriptor I/O operations.
- [lm75.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
