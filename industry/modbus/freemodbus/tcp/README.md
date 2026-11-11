# `industry/modbus/freemodbus/tcp`

## Overview
Implements `industry/modbus/freemodbus/tcp` source and header components (`mbtcp.c`, `mbtcp.h`) in the NuttX application tree.

## Interface
- [mbtcp.h:eMBTCPDoInit]
- [mbtcp.h:eMBTCPStart]
- [mbtcp.h:eMBTCPStop]
- [mbtcp.h:eMBTCPReceive]
- [mbtcp.h:eMBTCPSend]
- [mbtcp.h:MB_TCP_PSEUDO_ADDRESS]
- [mbtcp.c:eMBTCPDoInit]
- [mbtcp.c:eMBTCPStart]
- [mbtcp.c:eMBTCPStop]
- [mbtcp.c:eMBTCPReceive]
- [mbtcp.c:eMBTCPSend]

## Invariants
- [mbtcp.c:CONFIG_MB_TCP_ENABLED]: Conditional compilation gated by `CONFIG_MB_TCP_ENABLED`.

## Side Effects
- None

## Verification
- Run: `make test`
