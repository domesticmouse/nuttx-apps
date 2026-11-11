# `include`

## Overview
Architectural grouping for `include`, organizing `audioutils`, `builtin`, `canutils`, `fsutils`, `graphics`, `industry`, and 11 additional subdirectories.

## Subdirectories & Boundaries
- `audioutils`: [./audioutils/README.md](./audioutils/README.md) - Implements `include/audioutils` source and header components (`fmsynth.h`, `fmsynth_eg.h`, `fmsynth_op.h`, `mml_parser.h` and 1 more files) in the NuttX application tree.
- `builtin`: [./builtin/README.md](./builtin/README.md) - Implements `include/builtin`: Executes builtin applications registered during 'make context' time. New application is run in a separate task context (and thread).
- `canutils`: [./canutils/README.md](./canutils/README.md) - Implements `include/canutils`: Wrapper for CANIOC_SET_BITTIMING Input Parameter:
- `fsutils`: [./fsutils/README.md](./fsutils/README.md) - Implements `include/fsutils`: Call a block driver with the MDIOC_BULKERASE ioctl command. This will cause the MTD driver to erase all of the flash.
- `graphics`: [./graphics/README.md](./graphics/README.md) - Implements `include/graphics`: Start a new display list. This function will:
- `industry`: [./industry/README.md](./industry/README.md) - Implements `include/industry` source and header components (`abnt_codi.h`) in the NuttX application tree.
- `interpreters`: [./interpreters/README.md](./interpreters/README.md) - Implements `include/interpreters`: Interpret a BASIC script Input Parameters:
- `logging`: [./logging/README.md](./logging/README.md) - Architectural grouping for `include/logging`, organizing `nxscope`.
- `lte`: [./lte/README.md](./lte/README.md) - Implements `include/lte` source and header components (`lapi.h`, `lte_api.h`, `lte_fw_def.h`, `lte_fwupdate.h` and 2 more files) in the NuttX application tree.
- `modbus`: [./modbus/README.md](./modbus/README.md) - Implements `include/modbus` source and header components (`mb.h`, `mb_m.h`, `mbframe.h`, `mbfunc.h` and 3 more files) in the NuttX application tree.
- `netutils`: [./netutils/README.md](./netutils/README.md) - Implements `include/netutils`: Start the discover daemon. Input Parameters:
- `nshlib`: [./nshlib/README.md](./nshlib/README.md) - Implements `include/nshlib`: This interface is used to initialize the NuttShell (NSH).
- `nxmodbus`: [./nxmodbus/README.md](./nxmodbus/README.md) - Implements `include/nxmodbus`: Read coil values from a remote unit. Input Parameters:
- `platform`: [./platform/README.md](./platform/README.md) - Implements `include/platform`: Save platform-specific configuration data Input Parameter:
- `system`: [./system/README.md](./system/README.md) - Implements `include/system`: EMACS-like command line editor. This is actually more like readline than is the NuttX readline!
- `wasm`: [./wasm/README.md](./wasm/README.md) - Implements `include/wasm` source and header components (`math.h`) in the NuttX application tree.
- `wireless`: [./wireless/README.md](./wireless/README.md) - Implements `include/wireless` source and header components (`ieee802154.h`, `iwpan.h`, `wapi.h`) in the NuttX application tree.
