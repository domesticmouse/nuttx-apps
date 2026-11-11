# `wireless/ieee802154/libmac`

## Overview
Provides IEEE 802.15.4 MAC library routines (`wireless/ieee802154/libmac`). Some MAC library routines for ieee 802.15.4 apps

## Interface
- [Kconfig:CONFIG_IEEE802154_LIBMAC]
- [ieee802154_assocreq.c:ieee802154_assoc_req]
- [ieee802154_assocresp.c:ieee802154_assoc_resp]
- [ieee802154_disassocreq.c:ieee802154_disassoc_req]
- [ieee802154_getreq.c:ieee802154_get_req]
- [ieee802154_getreq.c:ieee802154_getchan]
- [ieee802154_getreq.c:ieee802154_geteaddr]
- [ieee802154_getreq.c:ieee802154_getsaddr]
- [ieee802154_getreq.c:ieee802154_getpanid]
- [ieee802154_getreq.c:ieee802154_getcoordeaddr]
- [ieee802154_getreq.c:ieee802154_getcoordsaddr]
- [ieee802154_getreq.c:ieee802154_getrxonidle]
- [ieee802154_getreq.c:ieee802154_getdevmode]
- [ieee802154_getreq.c:ieee802154_getpromisc]
- [ieee802154_getreq.c:ieee802154_gettxpwr]
- [ieee802154_getreq.c:ieee802154_getmaxretries]
- [ieee802154_getreq.c:ieee802154_getfcslen]
- [ieee802154_gtsreq.c:ieee802154_gts_req]

## Invariants
- [Kconfig:CONFIG_IEEE802154_LIBMAC]: Build and feature compilation gated by `CONFIG_IEEE802154_LIBMAC`.

## Side Effects
- [ieee802154_assocreq.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [ieee802154_assocreq.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [ieee802154_assocresp.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [ieee802154_assocresp.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [ieee802154_disassocreq.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [ieee802154_disassocreq.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
