# `netutils/smtp`

## Overview
Provides SMTP (`netutils/smtp`). Enable support for SMTP.

## Interface
- [Kconfig:CONFIG_NETUTILS_SMTP]
- [smtp.c:struct smtp_state]
- [smtp.c:smtp_configure]
- [smtp.c:smtp_send]
- [smtp.c:smtp_open]
- [smtp.c:smtp_close]

## Invariants
- [Kconfig:CONFIG_NETUTILS_SMTP]: Build and feature compilation gated by `CONFIG_NETUTILS_SMTP`.
- [Kconfig:depends on NET_IPv4]: Requires Kconfig dependency condition `NET_IPv4`.
- [Kconfig:depends on NET_TCP]: Requires Kconfig dependency condition `NET_TCP`.

## Side Effects
- [smtp.c:close]: Performs VFS file or device descriptor I/O operations.
- [smtp.c:recv]: Performs network socket creation, binding, or protocol I/O.
- [smtp.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
