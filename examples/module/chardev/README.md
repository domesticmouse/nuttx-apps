# chardev

## Overview
NuttX `module/chardev` component implementing `chardev.c`.

## Interface
- `[Makefile:PROGNAME]` - Registers application/module target `chardev`
- `[chardev.c:module_uninitialize]` - Public function `module_uninitialize()`
- `[chardev.c:module_initialize]` - Public function `module_initialize()`

## Invariants
- None

## Side Effects
- `[chardev.c:/dev/chardev]` - Opens or interacts with VFS/device path `/dev/chardev`
- `[chardev.c:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
