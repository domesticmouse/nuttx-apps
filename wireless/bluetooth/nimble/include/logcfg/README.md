# `wireless/bluetooth/nimble/include/logcfg`

## Overview
Implements `wireless/bluetooth/nimble/include/logcfg` source and header components (`logcfg.h`) in the NuttX application tree.

## Interface
- [logcfg.h:BLE_HS_LOG_DEBUG]
- [logcfg.h:BLE_HS_LOG_INFO]
- [logcfg.h:BLE_HS_LOG_WARN]
- [logcfg.h:BLE_HS_LOG_ERROR]
- [logcfg.h:BLE_HS_LOG_CRITICAL]
- [logcfg.h:BLE_HS_LOG_DISABLED]
- [logcfg.h:DFLT_LOG_DEBUG]
- [logcfg.h:DFLT_LOG_INFO]
- [logcfg.h:DFLT_LOG_WARN]
- [logcfg.h:DFLT_LOG_ERROR]
- [logcfg.h:DFLT_LOG_CRITICAL]
- [logcfg.h:DFLT_LOG_DISABLED]

## Invariants
- [logcfg.h:CONFIG_NIMBLE_DEBUG_ERROR]: Conditional compilation gated by `CONFIG_NIMBLE_DEBUG_ERROR`.
- [logcfg.h:CONFIG_NIMBLE_DEBUG_WARN]: Conditional compilation gated by `CONFIG_NIMBLE_DEBUG_WARN`.
- [logcfg.h:CONFIG_NIMBLE_DEBUG_INFO]: Conditional compilation gated by `CONFIG_NIMBLE_DEBUG_INFO`.

## Side Effects
- None

## Verification
- Run: `make test`
