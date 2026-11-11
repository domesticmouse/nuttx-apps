# `wireless/bluetooth/nimble/include/syscfg`

## Overview
Implements `wireless/bluetooth/nimble/include/syscfg` source and header components (`syscfg.h`) in the NuttX application tree.

## Interface
- [syscfg.h:MYNEWT_VAL]
- [syscfg.h:MYNEWT_VAL_CHOICE]
- [syscfg.h:MYNEWT_VAL_BLE_SOCK_USE_NUTTX]
- [syscfg.h:MYNEWT_VAL_NEWT_FEATURE_LOGCFG]
- [syscfg.h:MYNEWT_VAL_MSYS_1_BLOCK_COUNT]
- [syscfg.h:MYNEWT_VAL_MSYS_1_BLOCK_SIZE]
- [syscfg.h:MYNEWT_VAL_MSYS_2_BLOCK_COUNT]
- [syscfg.h:MYNEWT_VAL_MSYS_2_BLOCK_SIZE]
- [syscfg.h:MYNEWT_VAL_MSYS_1_SANITY_MIN_COUNT]
- [syscfg.h:MYNEWT_VAL_MSYS_2_SANITY_MIN_COUNT]
- [syscfg.h:MYNEWT_VAL_BLE_TRANSPORT_ACL_FROM_HS_COUNT]
- [syscfg.h:MYNEWT_VAL_BLE_TRANSPORT_ACL_FROM_LL_COUNT]
- [syscfg.h:MYNEWT_VAL_BLE_TRANSPORT_ACL_SIZE]
- [syscfg.h:MYNEWT_VAL_BLE_TRANSPORT_EVT_COUNT]
- [syscfg.h:MYNEWT_VAL_BLE_TRANSPORT_EVT_DISCARDABLE_COUNT]
- [syscfg.h:MYNEWT_VAL_BLE_TRANSPORT_EVT_SIZE]

## Invariants
- [syscfg.h:CONFIG_NIMBLE_TINYCRYPT]: Conditional compilation gated by `CONFIG_NIMBLE_TINYCRYPT`.
- [syscfg.h:CONFIG_NIMBLE_HS_FLOW_CTRL]: Conditional compilation gated by `CONFIG_NIMBLE_HS_FLOW_CTRL`.
- [syscfg.h:CONFIG_NIMBLE_ROLE_BROADCASTER]: Conditional compilation gated by `CONFIG_NIMBLE_ROLE_BROADCASTER`.
- [syscfg.h:CONFIG_NIMBLE_ROLE_CENTRAL]: Conditional compilation gated by `CONFIG_NIMBLE_ROLE_CENTRAL`.
- [syscfg.h:CONFIG_NIMBLE_ROLE_OBSERVER]: Conditional compilation gated by `CONFIG_NIMBLE_ROLE_OBSERVER`.
- [syscfg.h:CONFIG_NIMBLE_ROLE_PERIPHERAL]: Conditional compilation gated by `CONFIG_NIMBLE_ROLE_PERIPHERAL`.

## Side Effects
- None

## Verification
- Run: `make test`
