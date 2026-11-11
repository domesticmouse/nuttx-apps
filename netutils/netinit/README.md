# `netutils/netinit`

## Overview
Provides Network initialization (`netutils/netinit`). This option enables/disables all support for common network initialization.

## Interface
- [Kconfig:CONFIG_NETUTILS_NETINIT]
- [Kconfig:CONFIG_NETINIT_NETLOCAL]
- [Kconfig:CONFIG_NETINIT_THREAD]
- [Kconfig:CONFIG_NETINIT_MONITOR]
- [netinit.c:netinit_bringup]
- [netinit_associate.c:netinit_associate]

## Invariants
- [Kconfig:CONFIG_NETUTILS_NETINIT]: Build and feature compilation gated by `CONFIG_NETUTILS_NETINIT`.
- [Kconfig:CONFIG_NETINIT_NETLOCAL]: Build and feature compilation gated by `CONFIG_NETINIT_NETLOCAL`.
- [Kconfig:depends on NET]: Requires Kconfig dependency condition `NET`.
- [Kconfig:depends on !DISABLE_PTHREAD && !NETINIT_NETLOCAL]: Requires Kconfig dependency condition `!DISABLE_PTHREAD && !NETINIT_NETLOCAL`.
- [Kconfig:depends on ARCH_PHY_INTERRUPT && NETDEV_PHY_IOCTL && NET_UDP]: Requires Kconfig dependency condition `ARCH_PHY_INTERRUPT && NETDEV_PHY_IOCTL && NET_UDP`.
- [netinit.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ret < 0)` precondition.

## Side Effects
- [netinit.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [netinit.c:close]: Performs VFS file or device descriptor I/O operations.
- [netinit.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [netinit.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
