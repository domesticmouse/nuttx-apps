# `graphics/input/monkey`

## Overview
Implements `graphics/input/monkey`: Gets the next recorder state Returned Value:

## Interface
- [monkey.h:monkey_create]
- [monkey.h:monkey_update]
- [monkey.h:monkey_delete]
- [monkey.h:monkey_config_default_init]
- [monkey.h:monkey_set_config]
- [monkey.h:monkey_set_mode]
- [monkey.h:monkey_set_period]
- [monkey.h:monkey_set_recorder_path]
- [monkey_assert.h:MONKEY_ASSERT]
- [monkey_assert.h:MONKEY_ASSERT_NULL]
- [monkey_dev.h:struct monkey_dev_s]
- [monkey_dev.h:monkey_dev_create]
- [monkey_dev.h:monkey_dev_delete]
- [monkey_dev.h:monkey_dev_set_state]
- [monkey_dev.h:monkey_dev_get_state]
- [monkey_dev.h:monkey_dev_get_type]
- [monkey_dev.h:monkey_dev_get_available]
- [monkey_event.h:struct monkey_event_param_s]

## Invariants
- [monkey_assert.h:DEBUGASSERT]: Enforces `DEBUGASSERT(expr)` precondition.
- [monkey_main.c:CONFIG_VIDEO_FB]: Conditional compilation gated by `CONFIG_VIDEO_FB`.

## Side Effects
- [monkey.c:calloc]: Allocates or releases dynamic heap memory.
- [monkey_dev.c:read]: Performs VFS file or device descriptor I/O operations.
- [monkey_dev.c:calloc]: Allocates or releases dynamic heap memory.
- [monkey_log.c:syslog]: Writes formatted diagnostic, logging, or console output.
- [monkey_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [monkey_main.c:open]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
