# `include/nxmodbus`

## Overview
Implements `include/nxmodbus`: Read coil values from a remote unit. Input Parameters:

## Interface
- [nxmb_client.h:nxmb_read_coils]
- [nxmb_client.h:nxmb_read_discrete]
- [nxmb_client.h:nxmb_read_input]
- [nxmb_client.h:nxmb_read_holding]
- [nxmb_client.h:nxmb_write_coil]
- [nxmb_client.h:nxmb_write_holding]
- [nxmb_client.h:nxmb_write_coils]
- [nxmb_client.h:nxmb_write_holdings]
- [nxmb_client.h:nxmb_readwrite_holdings]
- [nxmb_client.h:nxmb_set_timeout]
- [nxmb_raw.h:nxmb_raw_submit_rx]
- [nxmb_raw.h:nxmb_raw_put_header]
- [nxmb_raw.h:nxmb_raw_get_header]
- [nxmb_raw.h:NXMB_RAW_HDR_SIZE]
- [nxmodbus.h:struct nxmb_adu_s]
- [nxmodbus.h:enum nxmb_mode_e]
- [nxmodbus.h:enum nxmb_parity_e]
- [nxmodbus.h:enum nxmb_regmode_e]

## Invariants
- [nxmodbus.h:CONFIG_NXMODBUS_CUSTOM_FC]: Conditional compilation gated by `CONFIG_NXMODBUS_CUSTOM_FC`.

## Side Effects
- None

## Verification
- Run: `make test`
