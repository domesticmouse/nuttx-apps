# `include/lte`

## Overview
Implements `include/lte` source and header components (`lapi.h`, `lte_api.h`, `lte_fw_def.h`, `lte_fwupdate.h` and 2 more files) in the NuttX application tree.

## Interface
- [lapi.h:lapi_evtinit]
- [lapi.h:lapi_evtdestoy]
- [lapi.h:lapi_evtyield]
- [lapi.h:lapi_req]
- [lte_api.h:lte_initialize]
- [lte_api.h:lte_finalize]
- [lte_api.h:lte_set_report_restart]
- [lte_api.h:lte_power_on]
- [lte_api.h:lte_power_off]
- [lte_api.h:lte_radio_on_sync]
- [lte_api.h:lte_radio_on]
- [lte_api.h:lte_radio_off_sync]
- [lte_api.h:lte_radio_off]
- [lte_api.h:lte_get_netinfo_sync]
- [lte_api.h:lte_get_netinfo]
- [lte_api.h:lte_activate_pdn_sync]
- [lte_api.h:lte_activate_pdn]
- [lte_api.h:lte_activate_pdn_cancel]

## Invariants
- [lte_api.h:CONFIG_LTE_LAPI_ENABLE_DEPRECATED_API]: Conditional compilation gated by `CONFIG_LTE_LAPI_ENABLE_DEPRECATED_API`.
- [lte_api.h:CONFIG_LTE_LAPI_KEEP_COMPATIBILITY]: Conditional compilation gated by `CONFIG_LTE_LAPI_KEEP_COMPATIBILITY`.
- [lte_log.h:CONFIG_LTE_LAPI_LOG_ACCESS]: Conditional compilation gated by `CONFIG_LTE_LAPI_LOG_ACCESS`.

## Side Effects
- None

## Verification
- Run: `make test`
