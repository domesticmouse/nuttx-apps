# `system/i2c`

## Overview
Provides I2C tool (`system/i2c`). Enable support for the I2C tool.

## Interface
- [Makefile:PROGNAME=i2c]
- [Kconfig:CONFIG_SYSTEM_I2CTOOL]
- [Kconfig:CONFIG_I2CTOOL_MINBUS]
- [Kconfig:CONFIG_I2CTOOL_MAXBUS]
- [Kconfig:CONFIG_I2CTOOL_MINADDR]
- [i2ctool.h:struct i2ctool_s]
- [i2ctool.h:struct cmdmap_s]
- [i2ctool.h:i2ctool_write]
- [i2ctool.h:i2ctool_printf]
- [i2ctool.h:i2ctool_flush]
- [i2ctool.h:i2ctool_hexdump]
- [i2ctool.h:i2ccmd_bus]
- [i2ctool.h:i2ccmd_dev]
- [i2ctool.h:i2ccmd_get]
- [i2ctool.h:i2ccmd_dump]
- [i2ctool.h:i2ccmd_set]
- [i2ctool.h:i2ccmd_verf]
- [i2ctool.h:i2ccmd_reset]

## Invariants
- [Kconfig:CONFIG_SYSTEM_I2CTOOL]: Build and feature compilation gated by `CONFIG_SYSTEM_I2CTOOL`.
- [Kconfig:CONFIG_I2CTOOL_MINBUS]: Build and feature compilation gated by `CONFIG_I2CTOOL_MINBUS`.
- [Kconfig:depends on I2C]: Requires Kconfig dependency condition `I2C`.
- [i2ctool.h:CONFIG_I2CTOOL_MINBUS]: Conditional compilation gated by `CONFIG_I2CTOOL_MINBUS`.
- [i2ctool.h:CONFIG_I2CTOOL_MAXBUS]: Conditional compilation gated by `CONFIG_I2CTOOL_MAXBUS`.
- [i2ctool.h:CONFIG_I2CTOOL_MINADDR]: Conditional compilation gated by `CONFIG_I2CTOOL_MINADDR`.

## Side Effects
- [i2c_dev.c:close]: Performs VFS file or device descriptor I/O operations.
- [i2c_devif.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [i2c_devif.c:open]: Performs VFS file or device descriptor I/O operations.
- [i2c_dump.c:close]: Performs VFS file or device descriptor I/O operations.
- [i2c_dump.c:calloc]: Allocates or releases dynamic heap memory.
- [i2c_dump.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
