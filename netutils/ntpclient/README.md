# `netutils/ntpclient`

## Overview
Provides NTP client (`netutils/ntpclient`). Enable support for the minimal NTP client.

## Interface
- [Kconfig:CONFIG_NETUTILS_NTPCLIENT]
- [Kconfig:CONFIG_NETUTILS_NTPCLIENT_SERVER]
- [Kconfig:CONFIG_NETUTILS_NTPCLIENT_SERVERIP]
- [Kconfig:CONFIG_NETUTILS_NTPCLIENT_PORTNO]
- [ntpv3.h:struct ntp_datagram_s]
- [ntpv3.h:struct ntp_datagram_with_key_s]
- [ntpv3.h:NTP_DATAGRAM_MINSIZE]
- [ntpv3.h:NTP_DATAGRAM_MAXSIZE]
- [ntpv3.h:MKLVM]
- [ntpv3.h:GETLI]
- [ntpv3.h:GETVN]
- [ntpv3.h:GETMODE]
- [ntpclient.c:enum ntpc_daemon_e]
- [ntpclient.c:enum ntpc_server_source_e]
- [ntpclient.c:struct ntpc_daemon_s]
- [ntpclient.c:union ntp_addr_u]
- [ntpclient.c:struct ntp_sample_s]
- [ntpclient.c:struct ntp_servers_s]

## Invariants
- [Kconfig:CONFIG_NETUTILS_NTPCLIENT]: Build and feature compilation gated by `CONFIG_NETUTILS_NTPCLIENT`.
- [Kconfig:CONFIG_NETUTILS_NTPCLIENT_SERVER]: Build and feature compilation gated by `CONFIG_NETUTILS_NTPCLIENT_SERVER`.
- [Kconfig:depends on NET_UDP && NET_SOCKOPTS]: Requires Kconfig dependency condition `NET_UDP && NET_SOCKOPTS`.
- [Kconfig:depends on LIBC_NETDB]: Requires Kconfig dependency condition `LIBC_NETDB`.
- [Kconfig:depends on !LIBC_NETDB]: Requires Kconfig dependency condition `!LIBC_NETDB`.
- [ntpv3.h:CONFIG_NETUTILS_NTPCLIENT_WITH_AUTH]: Conditional compilation gated by `CONFIG_NETUTILS_NTPCLIENT_WITH_AUTH`.

## Side Effects
- [ntpclient.c:close]: Performs VFS file or device descriptor I/O operations.
- [ntpclient.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [ntpclient.c:calloc]: Allocates or releases dynamic heap memory.
- [ntpclient.c:task_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
