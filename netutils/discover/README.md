# `netutils/discover`

## Overview
Provides Network Discovery Utility (`netutils/discover`). Tool for discovering devices on the local network per UDP broadcast.

## Interface
- [Kconfig:CONFIG_NETUTILS_DISCOVER]
- [Kconfig:CONFIG_DISCOVER_STACK_SIZE]
- [Kconfig:CONFIG_DISCOVER_PRIORITY]
- [Kconfig:CONFIG_DISCOVER_PORT]
- [discover.c:struct discover_state_s]
- [discover.c:discover_start]

## Invariants
- [Kconfig:CONFIG_NETUTILS_DISCOVER]: Build and feature compilation gated by `CONFIG_NETUTILS_DISCOVER`.
- [Kconfig:CONFIG_DISCOVER_STACK_SIZE]: Build and feature compilation gated by `CONFIG_DISCOVER_STACK_SIZE`.
- [Kconfig:depends on NET_UDP]: Requires Kconfig dependency condition `NET_UDP`.
- [discover.c:CONFIG_DISCOVER_STACK_SIZE]: Conditional compilation gated by `CONFIG_DISCOVER_STACK_SIZE`.
- [discover.c:CONFIG_DISCOVER_PRIORITY]: Conditional compilation gated by `CONFIG_DISCOVER_PRIORITY`.
- [discover.c:CONFIG_DISCOVER_PORT]: Conditional compilation gated by `CONFIG_DISCOVER_PORT`.

## Side Effects
- [discover.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [discover.c:close]: Performs VFS file or device descriptor I/O operations.
- [discover.c:recvfrom]: Performs network socket creation, binding, or protocol I/O.
- [discover.c:task_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
