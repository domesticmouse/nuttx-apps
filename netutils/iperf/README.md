# `netutils/iperf`

## Overview
Provides iperf example (`netutils/iperf`). Enable the \"iperf example\"

## Interface
- [Makefile:PROGNAME=$(CONFIG_NETUTILS_IPERF_PROGNAME)]
- [Kconfig:CONFIG_NETUTILS_IPERF]
- [Kconfig:CONFIG_NETUTILS_IPERF_PROGNAME]
- [Kconfig:CONFIG_NETUTILS_IPERF_PRIORITY]
- [Kconfig:CONFIG_NETUTILS_IPERF_STACKSIZE]
- [iperf.h:struct iperf_cfg_t]
- [iperf.h:iperf_start]
- [iperf.h:iperf_stop]
- [iperf.h:IPERF_FLAG_CLIENT]
- [iperf.h:IPERF_FLAG_SERVER]
- [iperf.h:IPERF_FLAG_TCP]
- [iperf.h:IPERF_FLAG_UDP]
- [iperf.h:IPERF_FLAG_LOCAL]
- [iperf.h:IPERF_FLAG_RPMSG]
- [iperf.c:struct iperf_ctrl_t]
- [iperf.c:struct iperf_udp_pkt_t]
- [iperf.c:iperf_start]
- [iperf.c:iperf_stop]

## Invariants
- [Kconfig:CONFIG_NETUTILS_IPERF]: Build and feature compilation gated by `CONFIG_NETUTILS_IPERF`.
- [Kconfig:CONFIG_NETUTILS_IPERF_PROGNAME]: Build and feature compilation gated by `CONFIG_NETUTILS_IPERF_PROGNAME`.
- [Kconfig:depends on NET]: Requires Kconfig dependency condition `NET`.
- [iperf.c:assert]: Enforces `assert(false)` precondition.
- [iperf.c:pthread_mutex_lock]: Synchronizes concurrent access across threads or critical sections.
- [iperf.c:pthread_mutex_unlock]: Synchronizes concurrent access across threads or critical sections.

## Side Effects
- [iperf.c:close]: Performs VFS file or device descriptor I/O operations.
- [iperf.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [iperf.c:free]: Allocates or releases dynamic heap memory.
- [iperf.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [iperf.c:printf]: Writes formatted diagnostic, logging, or console output.
- [iperf_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
