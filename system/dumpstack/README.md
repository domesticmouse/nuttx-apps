# `system/dumpstack`

## Overview
Provides dumpstack tool for show the task backtrace (`system/dumpstack`). This is the stack size that will be used when starting the dumpstack.

## Interface
- [Makefile:PROGNAME=dumpstack]
- [Kconfig:CONFIG_SYSTEM_DUMPSTACK]
- [Kconfig:CONFIG_SYSTEM_DUMPSTACK_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_DUMPSTACK_PRIORITY]
- [dumpstack.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_DUMPSTACK]: Build and feature compilation gated by `CONFIG_SYSTEM_DUMPSTACK`.
- [Kconfig:CONFIG_SYSTEM_DUMPSTACK_STACKSIZE]: Build and feature compilation gated by `CONFIG_SYSTEM_DUMPSTACK_STACKSIZE`.
- [Kconfig:depends on SCHED_BACKTRACE]: Requires Kconfig dependency condition `SCHED_BACKTRACE`.

## Side Effects
- None

## Verification
- Run: `make test`
