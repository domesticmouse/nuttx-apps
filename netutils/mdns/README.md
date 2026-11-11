# `netutils/mdns`

## Overview
Provides MDNS library (`netutils/mdns`). Enable the mDNS library. This allows calls to the library to be made. This external library is "unlicensed" using the methodology from

## Interface
- [Makefile:PROGNAME=$(CONFIG_NETUTILS_MDNS_PROGNAME)]
- [Kconfig:CONFIG_LIB_MDNS]
- [Kconfig:CONFIG_NETUTILS_MDNS]
- [Kconfig:CONFIG_NETUTILS_MDNS_PROGNAME]
- [Kconfig:CONFIG_NETUTILS_MDNS_PRIORITY]
- [mdnsd.c:enum mdnsd_daemon_e]
- [mdnsd.c:struct mdnsd_config_s]
- [mdnsd.c:mdnsd_stop]
- [mdnsd.c:mdnsd_start]

## Invariants
- [Kconfig:CONFIG_LIB_MDNS]: Build and feature compilation gated by `CONFIG_LIB_MDNS`.
- [Kconfig:CONFIG_NETUTILS_MDNS]: Build and feature compilation gated by `CONFIG_NETUTILS_MDNS`.
- [Kconfig:depends on NETUTILS_MDNS]: Requires Kconfig dependency condition `NETUTILS_MDNS`.
- [Kconfig:depends on NETUTILS_MDNS_DAEMON]: Requires Kconfig dependency condition `NETUTILS_MDNS_DAEMON`.
- [mdnsd.c:sem_wait]: Synchronizes concurrent access across threads or critical sections.

## Side Effects
- [mdnsd.c:posix_spawn]: Spawns child tasks, pthreads, or built-in applications.
- [mdnsd.c:syslog]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
