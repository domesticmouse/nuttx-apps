# `lte/lapi/src`

## Overview
Implements `lte/lapi/src` source and header components (`lapi_dbg.h`, `lapi_evt.c`, `lapi_firmware.c`, `lapi_log.c` and 9 more files) in the NuttX application tree.

## Interface
- [lapi_evt.c:lapi_evtinit]
- [lapi_evt.c:lapi_evtdestoy]
- [lapi_evt.c:lapi_evtyield]
- [lapi_evt.c:lapi_evtsend]
- [lapi_firmware.c:lte_get_version_sync]
- [lapi_firmware.c:ltefwupdate_initialize]
- [lapi_firmware.c:ltefwupdate_injectrest]
- [lapi_firmware.c:ltefwupdate_injected_datasize]
- [lapi_firmware.c:ltefwupdate_execute]
- [lapi_firmware.c:ltefwupdate_result]
- [lapi_firmware.c:lte_factory_reset_sync]
- [lapi_firmware.c:lte_get_version]
- [lapi_log.c:lte_log_collect]
- [lapi_log.c:lte_log_getlist]
- [lapi_log.c:lte_log_open]
- [lapi_log.c:lte_log_close]
- [lapi_log.c:lte_log_read]
- [lapi_log.c:lte_log_lseek]

## Invariants
- [lapi_dbg.h:CONFIG_LTE_LAPI_DEBUG_MSG]: Conditional compilation gated by `CONFIG_LTE_LAPI_DEBUG_MSG`.
- [lapi_firmware.c:CONFIG_LTE_LAPI_ENABLE_DEPRECATED_API]: Conditional compilation gated by `CONFIG_LTE_LAPI_ENABLE_DEPRECATED_API`.
- [lapi_log.c:CONFIG_LTE_LAPI_LOG_ACCESS]: Conditional compilation gated by `CONFIG_LTE_LAPI_LOG_ACCESS`.
- [lapi_net.c:CONFIG_LTE_LAPI_KEEP_COMPATIBILITY]: Conditional compilation gated by `CONFIG_LTE_LAPI_KEEP_COMPATIBILITY`.
- [lapi_net.c:CONFIG_LTE_LAPI_ENABLE_DEPRECATED_API]: Conditional compilation gated by `CONFIG_LTE_LAPI_ENABLE_DEPRECATED_API`.
- [lapi_pdn.c:CONFIG_LTE_LAPI_ENABLE_DEPRECATED_API]: Conditional compilation gated by `CONFIG_LTE_LAPI_ENABLE_DEPRECATED_API`.

## Side Effects
- [lapi_firmware.c:printf]: Writes formatted diagnostic, logging, or console output.
- [lapi_other.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [lapi_other.c:close]: Performs VFS file or device descriptor I/O operations.
- [lapi_other.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [lapi_power.c:close]: Performs VFS file or device descriptor I/O operations.
- [lapi_power.c:socket]: Performs network socket creation, binding, or protocol I/O.

## Verification
- Run: `make test`
