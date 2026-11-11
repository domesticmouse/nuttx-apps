# `wireless/ieee802154/i8sak`

## Overview
Provides IEEE 802.15.4 Swiss Army Knife (`wireless/ieee802154/i8sak`). Enable the IEEE 802.15.4 Swiss Army Knife

## Interface
- [Makefile:PROGNAME=$(CONFIG_IEEE802154_I8SAK_PROGNAME)]
- [Kconfig:CONFIG_IEEE802154_I8SAK]
- [Kconfig:CONFIG_IEEE802154_I8SAK_PROGNAME]
- [Kconfig:CONFIG_IEEE802154_I8SAK_PRIORITY]
- [Kconfig:CONFIG_IEEE802154_I8SAK_STACKSIZE]
- [i8sak.h:enum i8sak_mode_e]
- [i8sak.h:enum i8sak_cmd_e]
- [i8sak.h:struct i8sak_s]
- [i8sak.h:i8sak_requestdaemon]
- [i8sak.h:i8sak_releasedaemon]
- [i8sak.h:i8sak_cmd_abort]
- [i8sak.h:i8sak_char2nibble]
- [i8sak.h:i8sak_str2long]
- [i8sak.h:i8sak_str2luint8]
- [i8sak.h:i8sak_str2luint16]
- [i8sak.h:i8sak_str2bool]
- [i8sak.h:i8sak_str2payload]
- [i8sak.h:i8sak_str2eaddr]

## Invariants
- [Kconfig:CONFIG_IEEE802154_I8SAK]: Build and feature compilation gated by `CONFIG_IEEE802154_I8SAK`.
- [Kconfig:CONFIG_IEEE802154_I8SAK_PROGNAME]: Build and feature compilation gated by `CONFIG_IEEE802154_I8SAK_PROGNAME`.
- [i8sak.h:CONFIG_IEEE802154_I8SAK_DEFAULT_EP_EADDR]: Conditional compilation gated by `CONFIG_IEEE802154_I8SAK_DEFAULT_EP_EADDR`.
- [i8sak.h:CONFIG_IEEE802154_I8SAK_DEFAULT_EP_SADDR]: Conditional compilation gated by `CONFIG_IEEE802154_I8SAK_DEFAULT_EP_SADDR`.
- [i8sak.h:CONFIG_IEEE802154_I8SAK_DEFAULT_EP_PANID]: Conditional compilation gated by `CONFIG_IEEE802154_I8SAK_DEFAULT_EP_PANID`.
- [i8sak.h:CONFIG_NET_6LOWPAN]: Conditional compilation gated by `CONFIG_NET_6LOWPAN`.

## Side Effects
- [i8sak_acceptassoc.c:open]: Performs VFS file or device descriptor I/O operations.
- [i8sak_acceptassoc.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [i8sak_acceptassoc.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [i8sak_assoc.c:open]: Performs VFS file or device descriptor I/O operations.
- [i8sak_assoc.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [i8sak_assoc.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
