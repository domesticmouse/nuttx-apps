# `system/uorb/sensor`

## Overview
Implements `system/uorb/sensor` source and header components (`accel.c`, `accel.h`, `angle.c`, `angle.h` and 93 more files) in the NuttX application tree.

## Interface
- [topics.c:orb_get_meta]

## Invariants
- [accel.c:CONFIG_UORB_FORMAT]: Conditional compilation gated by `CONFIG_UORB_FORMAT`.
- [angle.c:CONFIG_UORB_FORMAT]: Conditional compilation gated by `CONFIG_UORB_FORMAT`.
- [baro.c:CONFIG_UORB_FORMAT]: Conditional compilation gated by `CONFIG_UORB_FORMAT`.
- [cap.c:CONFIG_UORB_FORMAT]: Conditional compilation gated by `CONFIG_UORB_FORMAT`.
- [charge.c:CONFIG_UORB_FORMAT]: Conditional compilation gated by `CONFIG_UORB_FORMAT`.
- [co2.c:CONFIG_UORB_FORMAT]: Conditional compilation gated by `CONFIG_UORB_FORMAT`.

## Side Effects
- [topics.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [topics.c:open]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
