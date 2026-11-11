# `wireless/ieee802154/libutils`

## Overview
Provides Common IEEE 802.15.4 library routines (`wireless/ieee802154/libutils`). Some common library routines for ieee 802.15.4 apps

## Interface
- [Kconfig:CONFIG_IEEE802154_LIBUTILS]
- [ieee802154_addrtostr.c:ieee802154_addrtostr]

## Invariants
- [Kconfig:CONFIG_IEEE802154_LIBUTILS]: Build and feature compilation gated by `CONFIG_IEEE802154_LIBUTILS`.
- [ieee802154_addrtostr.c:CONFIG_BIG_ENDIAN]: Conditional compilation gated by `CONFIG_BIG_ENDIAN`.

## Side Effects
- None

## Verification
- Run: `make test`
