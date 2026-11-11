# `system/uorb/uORB`

## Overview
Implements `system/uorb/uORB`: Open device node as advertiser / subscriber, register node and save meta in driver for first user, set buffer number for advertisers.

## Interface
- [internal.h:struct orb_loop_ops_s]
- [uORB.h:struct orb_metadata]
- [uORB.h:struct orb_state]
- [uORB.h:struct orb_object]
- [uORB.h:enum orb_loop_type_e]
- [uORB.h:struct orb_handle_s]
- [uORB.h:struct orb_loop_s]
- [uORB.h:orb_id_t]
- [uORB.h:orb_abstime]
- [uORB.h:orb_info_t]
- [uORB.h:orb_open]
- [uORB.h:orb_close]
- [uORB.h:orb_advertise_multi_queue_info]
- [uORB.h:orb_advertise_multi_queue]
- [uORB.h:orb_advertise]
- [uORB.h:orb_advertise_queue]
- [uORB.h:orb_advertise_multi]
- [uORB.h:orb_advertise_multi_queue_persist_info]

## Invariants
- [uORB.h:CONFIG_UORB_LOOP_MAX_EVENTS]: Conditional compilation gated by `CONFIG_UORB_LOOP_MAX_EVENTS`.
- [uORB.h:CONFIG_UORB_FORMAT]: Conditional compilation gated by `CONFIG_UORB_FORMAT`.
- [uORB.h:CONFIG_UORB_STORAGE_DIR]: Conditional compilation gated by `CONFIG_UORB_STORAGE_DIR`.
- [uORB.h:CONFIG_UORB_ALERT]: Conditional compilation gated by `CONFIG_UORB_ALERT`.
- [uORB.h:CONFIG_UORB_ERROR]: Conditional compilation gated by `CONFIG_UORB_ERROR`.
- [uORB.h:CONFIG_UORB_WARN]: Conditional compilation gated by `CONFIG_UORB_WARN`.

## Side Effects
- [uORB.h:syslog]: Writes formatted diagnostic, logging, or console output.
- [epoll.c:close]: Performs VFS file or device descriptor I/O operations.
- [loop.c:close]: Performs VFS file or device descriptor I/O operations.
- [uORB.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [uORB.c:open]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
