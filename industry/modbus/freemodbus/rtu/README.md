# `industry/modbus/freemodbus/rtu`

## Overview
Implements `industry/modbus/freemodbus/rtu` source and header components (`mbcrc.c`, `mbcrc.h`, `mbrtu.c`, `mbrtu.h` and 2 more files) in the NuttX application tree.

## Interface
- [mbcrc.h:usMBCRC16]
- [mbrtu.h:eMBRTUInit]
- [mbrtu.h:eMBRTUStart]
- [mbrtu.h:eMBRTUStop]
- [mbrtu.h:eMBRTUReceive]
- [mbrtu.h:eMBRTUSend]
- [mbrtu.h:xMBRTUReceiveFSM]
- [mbrtu.h:xMBRTUTransmitFSM]
- [mbrtu.h:xMBRTUTimerT15Expired]
- [mbrtu.h:xMBRTUTimerT35Expired]
- [mbrtu_m.h:eMBMasterRTUInit]
- [mbrtu_m.h:eMBMasterRTUStart]
- [mbrtu_m.h:eMBMasterRTUStop]
- [mbrtu_m.h:eMBMasterRTUReceive]
- [mbrtu_m.h:eMBMasterRTUSend]
- [mbrtu_m.h:xMBMasterRTUReceiveFSM]
- [mbrtu_m.h:xMBMasterRTUTransmitFSM]
- [mbrtu_m.h:xMBMasterRTUTimerExpired]

## Invariants
- [mbrtu.c:DEBUGASSERT]: Enforces `DEBUGASSERT(usRcvBufferPos < MB_SER_PDU_SIZE_MAX)` precondition.
- [mbrtu.c:DEBUGASSERT]: Enforces `DEBUGASSERT(eSndState == STATE_TX_IDLE)` precondition.
- [mbrtu.c:DEBUGASSERT]: Enforces `DEBUGASSERT(eRcvState == STATE_RX_IDLE)` precondition.
- [mbrtu.c:DEBUGASSERT]: Enforces `DEBUGASSERT((eRcvState == STATE_RX_INIT)` precondition.
- [mbrtu_m.c:DEBUGASSERT]: Enforces `DEBUGASSERT(usMasterRcvBufferPos < MB_SER_PDU_SIZE_MAX)` precondition.
- [mbrtu_m.c:DEBUGASSERT]: Enforces `DEBUGASSERT((eSndState == STATE_M_TX_IDLE)` precondition.

## Side Effects
- None

## Verification
- Run: `make test`
