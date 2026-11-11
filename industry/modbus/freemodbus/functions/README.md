# `industry/modbus/freemodbus/functions`

## Overview
Implements `industry/modbus/freemodbus/functions`: This function will request read discrete inputs. Input Parameters:

## Interface
- [mbfunccoils.c:prveMBError2Exception]
- [mbfunccoils.c:eMBFuncReadCoils]
- [mbfunccoils.c:eMBFuncWriteCoil]
- [mbfunccoils.c:eMBFuncWriteMultipleCoils]
- [mbfunccoils_m.c:prveMBError2Exception]
- [mbfunccoils_m.c:eMBMasterReqReadCoils]
- [mbfunccoils_m.c:eMBMasterFuncReadCoils]
- [mbfunccoils_m.c:eMBMasterReqWriteCoil]
- [mbfunccoils_m.c:eMBMasterFuncWriteCoil]
- [mbfunccoils_m.c:eMBMasterReqWriteMultipleCoils]
- [mbfunccoils_m.c:eMBMasterFuncWriteMultipleCoils]
- [mbfuncdisc.c:prveMBError2Exception]
- [mbfuncdisc.c:eMBFuncReadDiscreteInputs]
- [mbfuncdisc_m.c:prveMBError2Exception]
- [mbfuncdisc_m.c:eMBMasterReqReadDiscreteInputs]
- [mbfuncdisc_m.c:eMBMasterFuncReadDiscreteInputs]
- [mbfuncholding.c:prveMBError2Exception]
- [mbfuncholding.c:eMBFuncWriteHoldingRegister]

## Invariants
- [mbfunccoils.c:CONFIG_MB_FUNC_READ_COILS_ENABLED]: Conditional compilation gated by `CONFIG_MB_FUNC_READ_COILS_ENABLED`.
- [mbfunccoils.c:CONFIG_MB_FUNC_WRITE_COIL_ENABLED]: Conditional compilation gated by `CONFIG_MB_FUNC_WRITE_COIL_ENABLED`.
- [mbfunccoils.c:CONFIG_MB_FUNC_WRITE_MULTIPLE_COILS_ENABLED]: Conditional compilation gated by `CONFIG_MB_FUNC_WRITE_MULTIPLE_COILS_ENABLED`.
- [mbfunccoils_m.c:CONFIG_MB_RTU_MASTER]: Conditional compilation gated by `CONFIG_MB_RTU_MASTER`.
- [mbfunccoils_m.c:CONFIG_MB_ASCII_MASTER]: Conditional compilation gated by `CONFIG_MB_ASCII_MASTER`.
- [mbfunccoils_m.c:CONFIG_MB_MASTER_FUNC_READ_COILS_ENABLED]: Conditional compilation gated by `CONFIG_MB_MASTER_FUNC_READ_COILS_ENABLED`.

## Side Effects
- None

## Verification
- Run: `make test`
