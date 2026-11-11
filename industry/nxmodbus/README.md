# `industry/nxmodbus`

## Overview
Provides NxModbus - New Modbus Stack (`industry/nxmodbus`). NxModbus is a modern Modbus stack for NuttX with multi-instance support, per-instance register callbacks, and pluggable transport

## Interface
- [Kconfig:CONFIG_INDUSTRY_NXMODBUS]
- [Kconfig:CONFIG_NXMODBUS_SERVER]
- [Kconfig:CONFIG_NXMODBUS_CLIENT]
- [Kconfig:CONFIG_NXMODBUS_RTU]
- [nxmb_internal.h:struct nxmb_transport_ops_s]
- [nxmb_internal.h:struct nxmb_custom_fc_s]
- [nxmb_internal.h:struct nxmb_context_s]
- [nxmb_internal.h:nxmb_cb_ret_to_exception]
- [nxmb_internal.h:nxmb_util_get_u16_be]
- [nxmb_internal.h:nxmb_util_put_u16_be]
- [nxmb_internal.h:nxmb_util_clock_ms]
- [nxmb_internal.h:nxmb_serial_configure]
- [nxmb_internal.h:nxmb_util_set_bits]
- [nxmb_internal.h:nxmb_util_get_bits]
- [nxmb_internal.h:nxmb_crc16]
- [nxmb_internal.h:nxmb_lrc]
- [nxmb_internal.h:nxmb_client_init]
- [nxmb_internal.h:nxmb_client_deinit]
- `core`: [./core/README.md](./core/README.md) - Implements `industry/nxmodbus/core`: Create a new NxModbus instance. Input Parameters:
- `transport`: [./transport/README.md](./transport/README.md) - Implements `industry/nxmodbus/transport`: Calculate Modbus ASCII LRC checksum. Input Parameters:

## Invariants
- [Kconfig:CONFIG_INDUSTRY_NXMODBUS]: Build and feature compilation gated by `CONFIG_INDUSTRY_NXMODBUS`.
- [Kconfig:CONFIG_NXMODBUS_SERVER]: Build and feature compilation gated by `CONFIG_NXMODBUS_SERVER`.
- [Kconfig:depends on NET_TCP]: Requires Kconfig dependency condition `NET_TCP`.
- [Kconfig:depends on NXMODBUS_ASCII]: Requires Kconfig dependency condition `NXMODBUS_ASCII`.
- [Kconfig:depends on NXMODBUS_CLIENT]: Requires Kconfig dependency condition `NXMODBUS_CLIENT`.
- [nxmb_internal.h:CONFIG_NXMODBUS_RTU]: Conditional compilation gated by `CONFIG_NXMODBUS_RTU`.

## Side Effects
- None

## Verification
- Run: `make test`
