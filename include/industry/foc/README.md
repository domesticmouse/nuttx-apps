# `include/industry/foc`

## Overview
Implements `include/industry/foc` source and header components (`foc_common.h`, `foc_log.h`, `foc_utils.h`) in the NuttX application tree.

## Interface
- [foc_common.h:enum foc_handler_mode_e]
- [foc_common.h:enum foc_number_type_e]
- [foc_common.h:enum foc_ramp_mode_e]
- [foc_common.h:enum foc_angle_type_e]
- [foc_common.h:enum foc_openloop_stage_e]
- [foc_log.h:FOCLIBLOG]
- [foc_log.h:FOCLIBERR]
- [foc_log.h:FOCLIBWARN]
- [foc_utils.h:foc_dev_stop]
- [foc_utils.h:foc_dev_start]
- [foc_utils.h:foc_dev_clearfault]
- [foc_utils.h:foc_dev_getstate]
- [foc_utils.h:foc_dev_setparams]
- [foc_utils.h:foc_dev_setcfg]
- [foc_utils.h:foc_dev_getcfg]
- [foc_utils.h:foc_dev_getinfo]
- [foc_utils.h:foc_cfg_print]
- `fixed16`: [./fixed16/README.md](./fixed16/README.md) - Implements `include/industry/foc/fixed16` source and header components (`foc_align.h`, `foc_angle.h`, `foc_cordic.h`, `foc_feedforward.h` and 6 more files) in the NuttX application tree.
- `float`: [./float/README.md](./float/README.md) - Implements `include/industry/foc/float` source and header components (`foc_align.h`, `foc_angle.h`, `foc_cordic.h`, `foc_feedforward.h` and 6 more files) in the NuttX application tree.

## Invariants
- [foc_common.h:CONFIG_INDUSTRY_FOC_FLOAT]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_FLOAT`.
- [foc_common.h:CONFIG_INDUSTRY_FOC_FIXED16]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_FIXED16`.
- [foc_log.h:CONFIG_INDUSTRY_FOC_DEBUG]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_DEBUG`.
- [foc_log.h:CONFIG_INDUSTRY_FOC_ERROR]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_ERROR`.
- [foc_log.h:CONFIG_INDUSTRY_FOC_WARN]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_WARN`.

## Side Effects
- [foc_log.h:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
