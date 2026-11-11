# `industry/nxmodbus/transport`

## Overview
Implements `industry/nxmodbus/transport`: Calculate Modbus ASCII LRC checksum. Input Parameters:

## Interface
- [nxmb_ascii.c:struct nxmb_ascii_state_s]
- [nxmb_crc.c:nxmb_crc16]
- [nxmb_lrc.c:nxmb_lrc]
- [nxmb_raw.c:struct nxmb_raw_state_s]
- [nxmb_raw.c:nxmb_raw_submit_rx]
- [nxmb_raw.c:nxmb_raw_put_header]
- [nxmb_raw.c:nxmb_raw_get_header]
- [nxmb_serial.c:struct nxmb_serial_state_s]
- [nxmb_serial_common.c:nxmb_serial_configure]
- [nxmb_tcp.c:struct nxmb_tcp_client_s]
- [nxmb_tcp.c:struct nxmb_tcp_state_s]

## Invariants
- [nxmb_ascii.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx)` precondition.
- [nxmb_ascii.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx && ctx->transport_state)` precondition.
- [nxmb_ascii.c:CONFIG_SERIAL_TERMIOS]: Conditional compilation gated by `CONFIG_SERIAL_TERMIOS`.
- [nxmb_raw.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx)` precondition.
- [nxmb_raw.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx && ctx->transport_state)` precondition.
- [nxmb_raw.c:DEBUGASSERT]: Enforces `DEBUGASSERT(ctx && adu)` precondition.

## Side Effects
- [nxmb_ascii.c:open]: Performs VFS file or device descriptor I/O operations.
- [nxmb_ascii.c:calloc]: Allocates or releases dynamic heap memory.
- [nxmb_raw.c:malloc]: Allocates or releases dynamic heap memory.
- [nxmb_serial.c:open]: Performs VFS file or device descriptor I/O operations.
- [nxmb_serial.c:calloc]: Allocates or releases dynamic heap memory.
- [nxmb_tcp.c:close]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
