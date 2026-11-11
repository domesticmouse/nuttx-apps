# `system/sensortest`

## Overview
Provides Sensor driver test (`system/sensortest`). Enable the Sensor driver test

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_SENSORTEST_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_SENSORTEST]
- [Kconfig:CONFIG_SYSTEM_SENSORTEST_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_SENSORTEST_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_SENSORTEST_STACKSIZE]
- [sensortest.c:struct sensor_info]
- [sensortest.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_SENSORTEST]: Build and feature compilation gated by `CONFIG_SYSTEM_SENSORTEST`.
- [Kconfig:CONFIG_SYSTEM_SENSORTEST_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_SENSORTEST_PROGNAME`.
- [Kconfig:depends on SENSORS && ENABLE_ALL_SIGNALS]: Requires Kconfig dependency condition `SENSORS && ENABLE_ALL_SIGNALS`.

## Side Effects
- [sensortest.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [sensortest.c:open]: Performs VFS file or device descriptor I/O operations.
- [sensortest.c:calloc]: Allocates or releases dynamic heap memory.
- [sensortest.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
