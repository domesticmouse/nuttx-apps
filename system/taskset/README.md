# `system/taskset`

## Overview
Provides Taskset Command (`system/taskset`). Enable support for the taskset command.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_TASKSET_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_TASKSET]
- [Kconfig:CONFIG_SYSTEM_TASKSET_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_TASKSET_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_TASKSET_STACKSIZE]
- [taskset.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_TASKSET]: Build and feature compilation gated by `CONFIG_SYSTEM_TASKSET`.
- [Kconfig:CONFIG_SYSTEM_TASKSET_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_TASKSET_PROGNAME`.
- [Kconfig:depends on SMP && SYSTEM_SYSTEM]: Requires Kconfig dependency condition `SMP && SYSTEM_SYSTEM`.
- [taskset.c:DEBUGASSERT]: Enforces `DEBUGASSERT(NULL != arg)` precondition.

## Side Effects
- [taskset.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
