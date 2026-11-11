# `system/irtest`

## Overview
Provides IR driver test (`system/irtest`). Enable the IR driver test

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_IRTEST_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_IRTEST]
- [Kconfig:CONFIG_SYSTEM_IRTEST_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_IRTEST_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_IRTEST_STACKSIZE]
- [cmd.hpp:struct arg]
- [cmd.hpp:struct cmd]
- [cmd.hpp:get_first_arg]
- [cmd.hpp:get_next_arg]
- [cmd.hpp:init_device]
- [cmd.hpp:CMD0]
- [cmd.hpp:CMD1]
- [cmd.hpp:CMD2]
- [cmd.hpp:CMD3]
- [enum.hpp:struct enum_value]
- [enum.hpp:struct enum_type]
- [cmd.cxx:init_device]
- [main.cxx:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_IRTEST]: Build and feature compilation gated by `CONFIG_SYSTEM_IRTEST`.
- [Kconfig:CONFIG_SYSTEM_IRTEST_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_IRTEST_PROGNAME`.
- [Kconfig:depends on DRIVERS_RC]: Requires Kconfig dependency condition `DRIVERS_RC`.
- [cmd.cxx:pthread_mutex_lock]: Synchronizes concurrent access across threads or critical sections.
- [cmd.cxx:pthread_mutex_unlock]: Synchronizes concurrent access across threads or critical sections.
- [main.cxx:CONFIG_LINE_MAX]: Conditional compilation gated by `CONFIG_LINE_MAX`.

## Side Effects
- [cmd.cxx:ioctl]: Issues device/driver control requests via `ioctl()`.
- [cmd.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [cmd.cxx:printf]: Writes formatted diagnostic, logging, or console output.
- [main.cxx:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
