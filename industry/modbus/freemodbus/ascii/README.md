# `industry/modbus/freemodbus/ascii`

## Overview
Implements `industry/modbus/freemodbus/ascii` source and header components (`mbascii.c`, `mbascii.h`) in the NuttX application tree.

## Interface
- [mbascii.h:eMBASCIIInit]
- [mbascii.h:eMBASCIIStart]
- [mbascii.h:eMBASCIIStop]
- [mbascii.h:eMBASCIIReceive]
- [mbascii.h:eMBASCIISend]
- [mbascii.h:xMBASCIIReceiveFSM]
- [mbascii.h:xMBASCIITransmitFSM]
- [mbascii.h:xMBASCIITimerT1SExpired]
- [mbascii.c:eMBRcvState]
- [mbascii.c:eMBSndState]
- [mbascii.c:eMBBytePos]
- [mbascii.c:eMBASCIIInit]
- [mbascii.c:eMBASCIIStart]
- [mbascii.c:eMBASCIIStop]
- [mbascii.c:eMBASCIIReceive]
- [mbascii.c:eMBASCIISend]
- [mbascii.c:xMBASCIIReceiveFSM]
- [mbascii.c:xMBASCIITransmitFSM]

## Invariants
- [mbascii.h:CONFIG_MB_ASCII_ENABLED]: Conditional compilation gated by `CONFIG_MB_ASCII_ENABLED`.
- [mbascii.c:DEBUGASSERT]: Enforces `DEBUGASSERT(0)` precondition.
- [mbascii.c:DEBUGASSERT]: Enforces `DEBUGASSERT(usRcvBufferPos < MB_SER_PDU_SIZE_MAX)` precondition.
- [mbascii.c:DEBUGASSERT]: Enforces `DEBUGASSERT(eSndState == STATE_TX_IDLE)` precondition.
- [mbascii.c:DEBUGASSERT]: Enforces `DEBUGASSERT(eRcvState == STATE_RX_IDLE)` precondition.
- [mbascii.c:DEBUGASSERT]: Enforces `DEBUGASSERT(eRcvState == STATE_RX_RCV || eRcvState == STATE_RX_WAIT_EOF)` precondition.

## Side Effects
- None

## Verification
- Run: `make test`
