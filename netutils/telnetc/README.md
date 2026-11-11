# `netutils/telnetc`

## Overview
Provides Telnet client library (`netutils/telnetc`). Enable support for the libtelnet. This is a public domain Telnet client library available from https://github.com/seanmiddleditch/libtelnet

## Interface
- [Kconfig:CONFIG_NETUTILS_TELNETC]
- [telnetc.c:enum telnet_state_e]
- [telnetc.c:struct telnet_s]
- [telnetc.c:struct telnet_rfc1143_s]
- [telnetc.c:telnet_init]
- [telnetc.c:telnet_free]
- [telnetc.c:telnet_recv]
- [telnetc.c:telnet_iac]
- [telnetc.c:telnet_negotiate]
- [telnetc.c:telnet_send]
- [telnetc.c:telnet_begin_sb]
- [telnetc.c:telnet_subnegotiation]
- [telnetc.c:telnet_begin_compress2]
- [telnetc.c:telnet_vprintf]
- [telnetc.c:telnet_printf]
- [telnetc.c:telnet_raw_vprintf]
- [telnetc.c:telnet_raw_printf]
- [telnetc.c:telnet_begin_newenviron]

## Invariants
- [Kconfig:CONFIG_NETUTILS_TELNETC]: Build and feature compilation gated by `CONFIG_NETUTILS_TELNETC`.
- [Kconfig:depends on NET && NET_TCP]: Requires Kconfig dependency condition `NET && NET_TCP`.

## Side Effects
- [telnetc.c:calloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
