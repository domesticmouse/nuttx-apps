# `include/wireless`

## Overview
Implements `include/wireless` source and header components (`ieee802154.h`, `iwpan.h`, `wapi.h`) in the NuttX application tree.

## Interface
- [ieee802154.h:ieee802154_assoc_req]
- [ieee802154.h:ieee802154_assoc_resp]
- [ieee802154.h:ieee802154_disassoc_req]
- [ieee802154.h:ieee802154_get_req]
- [ieee802154.h:ieee802154_gts_req]
- [ieee802154.h:ieee802154_orphan_resp]
- [ieee802154.h:ieee802154_reset_req]
- [ieee802154.h:ieee802154_rxenable_req]
- [ieee802154.h:ieee802154_scan_req]
- [ieee802154.h:ieee802154_set_req]
- [ieee802154.h:ieee802154_start_req]
- [ieee802154.h:ieee802154_sync_req]
- [ieee802154.h:ieee802154_poll_req]
- [ieee802154.h:ieee802154_dps_req]
- [ieee802154.h:ieee802154_sounding_req]
- [ieee802154.h:ieee802154_calibrate_req]
- [ieee802154.h:ieee802154_setchan]
- [ieee802154.h:ieee802154_getchan]

## Invariants
- [ieee802154.h:CONFIG_NET_6LOWPAN]: Conditional compilation gated by `CONFIG_NET_6LOWPAN`.
- [wapi.h:CONFIG_WIRELESS_WAPI_INITCONF]: Conditional compilation gated by `CONFIG_WIRELESS_WAPI_INITCONF`.
- [wapi.h:CONFIG_NET_ROUTE]: Conditional compilation gated by `CONFIG_NET_ROUTE`.

## Side Effects
- None

## Verification
- Run: `make test`
