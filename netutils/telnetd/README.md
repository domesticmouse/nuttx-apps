# `netutils/telnetd`

## Overview
Provides Telnet daemon (`netutils/telnetd`). Enable support for the Telnet daemon.

## Interface
- [Kconfig:CONFIG_NETUTILS_TELNETD]
- [telnetd_daemon.c:addr]
- [telnetd_daemon.c:telnetd_daemon]

## Invariants
- [Kconfig:CONFIG_NETUTILS_TELNETD]: Build and feature compilation gated by `CONFIG_NETUTILS_TELNETD`.
- [Kconfig:depends on NET && NET_TCP]: Requires Kconfig dependency condition `NET && NET_TCP`.
- [telnetd_daemon.c:CONFIG_SCHED_HAVE_PARENT]: Conditional compilation gated by `CONFIG_SCHED_HAVE_PARENT`.
- [telnetd_daemon.c:CONFIG_ENABLE_ALL_SIGNALS]: Conditional compilation gated by `CONFIG_ENABLE_ALL_SIGNALS`.
- [telnetd_daemon.c:CONFIG_NET_SOCKOPTS]: Conditional compilation gated by `CONFIG_NET_SOCKOPTS`.
- [telnetd_daemon.c:CONFIG_NET_SOLINGER]: Conditional compilation gated by `CONFIG_NET_SOLINGER`.

## Side Effects
- [telnetd_daemon.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [telnetd_daemon.c:open]: Performs VFS file or device descriptor I/O operations.
- [telnetd_daemon.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [telnetd_daemon.c:task_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
