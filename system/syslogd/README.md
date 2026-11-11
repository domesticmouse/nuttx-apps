# `system/syslogd`

## Overview
Provides syslogd utility (`system/syslogd`). Enable support for the 'syslogd' utility. This utility will read syslog messages from the syslog device and transmit them over UDP in RFC 5424

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_SYSLOGD_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_SYSLOGD]
- [Kconfig:CONFIG_SYSTEM_SYSLOGD_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_SYSLOGD_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_SYSLOGD_STACKSIZE]
- [syslogd_main.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_SYSLOGD]: Build and feature compilation gated by `CONFIG_SYSTEM_SYSLOGD`.
- [Kconfig:CONFIG_SYSTEM_SYSLOGD_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_SYSLOGD_PROGNAME`.
- [Kconfig:depends on NET_UDP && SYSLOG_RFC5424]: Requires Kconfig dependency condition `NET_UDP && SYSLOG_RFC5424`.
- [syslogd_main.c:CONFIG_LIBC_EXECFUNCS]: Conditional compilation gated by `CONFIG_LIBC_EXECFUNCS`.
- [syslogd_main.c:CONFIG_SYSTEM_SYSLOGD_ENTRYSIZE]: Conditional compilation gated by `CONFIG_SYSTEM_SYSLOGD_ENTRYSIZE`.

## Side Effects
- [syslogd_main.c:open]: Performs VFS file or device descriptor I/O operations.
- [syslogd_main.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [syslogd_main.c:posix_spawn]: Spawns child tasks, pthreads, or built-in applications.
- [syslogd_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
