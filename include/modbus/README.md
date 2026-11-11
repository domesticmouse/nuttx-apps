# `include/modbus`

## Overview
Implements `include/modbus` source and header components (`mb.h`, `mb_m.h`, `mbframe.h`, `mbfunc.h` and 3 more files) in the NuttX application tree.

## Interface
- [mb.h:eMBMode]
- [mb.h:eMBRegisterMode]
- [mb.h:eMBErrorCode]
- [mb.h:eMBInit]
- [mb.h:eMBTCPInit]
- [mb.h:eMBClose]
- [mb.h:eMBEnable]
- [mb.h:eMBDisable]
- [mb.h:eMBPoll]
- [mb.h:eMBSetSlaveID]
- [mb.h:eMBRegisterCB]
- [mb.h:eMBRegInputCB]
- [mb.h:eMBRegHoldingCB]
- [mb.h:eMBRegCoilsCB]
- [mb.h:eMBRegDiscreteCB]
- [mb_m.h:eMBMasterReqErrCode]
- [mb_m.h:eMBMasterTimerMode]
- [mb_m.h:eMBMasterInit]

## Invariants
- [mbfunc.h:CONFIG_MB_FUNC_OTHER_REP_SLAVEID_BUF]: Conditional compilation gated by `CONFIG_MB_FUNC_OTHER_REP_SLAVEID_BUF`.
- [mbfunc.h:CONFIG_MB_FUNC_READ_INPUT_ENABLED]: Conditional compilation gated by `CONFIG_MB_FUNC_READ_INPUT_ENABLED`.
- [mbfunc.h:CONFIG_MB_FUNC_READ_HOLDING_ENABLED]: Conditional compilation gated by `CONFIG_MB_FUNC_READ_HOLDING_ENABLED`.
- [mbfunc.h:CONFIG_MB_FUNC_WRITE_HOLDING_ENABLED]: Conditional compilation gated by `CONFIG_MB_FUNC_WRITE_HOLDING_ENABLED`.
- [mbfunc.h:CONFIG_MB_FUNC_WRITE_MULTIPLE_HOLDING_ENABLED]: Conditional compilation gated by `CONFIG_MB_FUNC_WRITE_MULTIPLE_HOLDING_ENABLED`.
- [mbfunc.h:CONFIG_MB_FUNC_READ_COILS_ENABLED]: Conditional compilation gated by `CONFIG_MB_FUNC_READ_COILS_ENABLED`.

## Side Effects
- None

## Verification
- Run: `make test`
