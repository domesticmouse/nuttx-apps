# `system/nxinit`

## Overview
Provides NuttX Init (`system/nxinit`). Enable NxInit(NuttX Init) component for system initialization. The script of NxInit(init.rc) is compatible with the Android Init Language syntax.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_NXINIT_PROGNAME)]
- [Makefile:PROGNAME=nxinit_unit_test]
- [Kconfig:CONFIG_SYSTEM_NXINIT]
- [Kconfig:CONFIG_SYSTEM_NXINIT_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_NXINIT_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_NXINIT_PROGNAME]
- [action.h:enum action_cmd_op_e]
- [action.h:struct action_cmd_s]
- [action.h:struct action_event_s]
- [action.h:struct action_s]
- [action.h:struct action_manager_s]
- [action.h:enum action_event_state_e]
- [action.h:init_action_add_event]
- [action.h:init_action_run_command]
- [action.h:init_action_reap_command]
- [action.h:init_action_parse]
- [action.h:init_action_foreach_event]
- [action.h:init_action_trigger_event]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXINIT]: Build and feature compilation gated by `CONFIG_SYSTEM_NXINIT`.
- [Kconfig:CONFIG_SYSTEM_NXINIT_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_NXINIT_PRIORITY`.
- [Kconfig:depends on LIBC_EXECFUNCS]: Requires Kconfig dependency condition `LIBC_EXECFUNCS`.
- [Kconfig:depends on SCHED_CHILD_STATUS]: Requires Kconfig dependency condition `SCHED_CHILD_STATUS`.
- [Kconfig:depends on SYSTEM_NXINIT_WARN]: Requires Kconfig dependency condition `SYSTEM_NXINIT_WARN`.
- [action.h:CONFIG_BMP]: Conditional compilation gated by `CONFIG_BMP`.

## Side Effects
- [init.h:printf]: Writes formatted diagnostic, logging, or console output.
- [action.c:free]: Allocates or releases dynamic heap memory.
- [builtin.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [builtin.c:open]: Performs VFS file or device descriptor I/O operations.
- [parser.c:open]: Performs VFS file or device descriptor I/O operations.
- [parser.c:free]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
