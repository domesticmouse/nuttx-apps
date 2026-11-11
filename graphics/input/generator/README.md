# `graphics/input/generator`

## Overview
Implements `graphics/input/generator`: Get the input generator device by type. Input Parameters:

## Interface
- [input_gen_internal.h:struct input_gen_dev_s]
- [input_gen_internal.h:input_gen_search_dev]
- [input_gen_internal.h:input_gen_dev2path]
- [input_gen_internal.h:input_gen_utouch_write]
- [input_gen_internal.h:input_gen_ubutton_write]
- [input_gen_internal.h:input_gen_umouse_write]
- [input_gen_internal.h:input_gen_grab]
- [input_gen_internal.h:input_gen_ungrab]
- [input.c:struct input_cmd_s]
- [input.c:main]
- [input_gen_ctx.c:struct input_gen_ctx_s]
- [input_gen_ctx.c:input_gen_create]
- [input_gen_ctx.c:input_gen_destroy]
- [input_gen_ctx.c:input_gen_search_dev]
- [input_gen_ctx.c:input_gen_query_device]
- [input_gen_ctx.c:input_gen_reset_devices]
- [input_gen_ctx.c:input_gen_write_raw]
- [input_gen_dev.c:input_gen_dev2path]

## Invariants
- [input_gen_internal.h:CONFIG_INPUT_MOUSE_WHEEL]: Conditional compilation gated by `CONFIG_INPUT_MOUSE_WHEEL`.
- [input_gen_dev.c:CONFIG_INPUT_MOUSE_WHEEL]: Conditional compilation gated by `CONFIG_INPUT_MOUSE_WHEEL`.
- [input_gen_dev.c:CONFIG_FS_LOCK_BUCKET_SIZE]: Conditional compilation gated by `CONFIG_FS_LOCK_BUCKET_SIZE`.
- [input_gen_event.c:CONFIG_INPUT_MOUSE_WHEEL]: Conditional compilation gated by `CONFIG_INPUT_MOUSE_WHEEL`.

## Side Effects
- [input.c:printf]: Writes formatted diagnostic, logging, or console output.
- [input_gen_ctx.c:open]: Performs VFS file or device descriptor I/O operations.
- [input_gen_ctx.c:zalloc]: Allocates or releases dynamic heap memory.
- [input_gen_dev.c:write]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
