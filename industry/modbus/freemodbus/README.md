# `industry/modbus/freemodbus`

## Overview
Provides FreeModBus (`industry/modbus/freemodbus`). Maximum number of Modbus functions codes the protocol stack should support.

## Interface
- [Kconfig:CONFIG_INDUSTRY_MODBUS]
- [Kconfig:CONFIG_MB_FUNC_HANDLERS_MAX]
- [Kconfig:CONFIG_INDUSTRY_MODBUS_SLAVE]
- [Kconfig:CONFIG_MB_ASCII_ENABLED]
- [mb.c:eMBInit]
- [mb.c:eMBTCPInit]
- [mb.c:eMBRegisterCB]
- [mb.c:eMBClose]
- [mb.c:eMBEnable]
- [mb.c:eMBDisable]
- [mb.c:eMBPoll]
- [mb_m.c:eMBMasterInit]
- [mb_m.c:eMBMasterClose]
- [mb_m.c:eMBMasterEnable]
- [mb_m.c:eMBMasterDisable]
- [mb_m.c:eMBMasterPoll]
- [mb_m.c:xMBMasterGetCBRunInMasterMode]
- [mb_m.c:vMBMasterSetCBRunInMasterMode]
- `ascii`: [./ascii/README.md](./ascii/README.md) - Implements `industry/modbus/freemodbus/ascii` source and header components (`mbascii.c`, `mbascii.h`) in the NuttX application tree.
- `functions`: [./functions/README.md](./functions/README.md) - Implements `industry/modbus/freemodbus/functions`: This function will request read discrete inputs. Input Parameters:
- `nuttx`: [./nuttx/README.md](./nuttx/README.md) - Implements `industry/modbus/freemodbus/nuttx` source and header components (`port.h`, `portevent.c`, `portevent_m.c`, `portother.c` and 5 more files) in the NuttX application tree.
- `rtu`: [./rtu/README.md](./rtu/README.md) - Implements `industry/modbus/freemodbus/rtu` source and header components (`mbcrc.c`, `mbcrc.h`, `mbrtu.c`, `mbrtu.h` and 2 more files) in the NuttX application tree.
- `tcp`: [./tcp/README.md](./tcp/README.md) - Implements `industry/modbus/freemodbus/tcp` source and header components (`mbtcp.c`, `mbtcp.h`) in the NuttX application tree.

## Invariants
- [Kconfig:CONFIG_INDUSTRY_MODBUS]: Build and feature compilation gated by `CONFIG_INDUSTRY_MODBUS`.
- [Kconfig:CONFIG_MB_FUNC_HANDLERS_MAX]: Build and feature compilation gated by `CONFIG_MB_FUNC_HANDLERS_MAX`.
- [Kconfig:depends on MB_TCP_ENABLED]: Requires Kconfig dependency condition `MB_TCP_ENABLED`.
- [Kconfig:depends on MB_ASCII_ENABLED]: Requires Kconfig dependency condition `MB_ASCII_ENABLED`.
- [Kconfig:depends on MB_FUNC_OTHER_REP_SLAVEID_ENABLED]: Requires Kconfig dependency condition `MB_FUNC_OTHER_REP_SLAVEID_ENABLED`.
- [mb.c:CONFIG_MB_RTU_ENABLED]: Conditional compilation gated by `CONFIG_MB_RTU_ENABLED`.

## Side Effects
- None

## Verification
- Run: `make test`
