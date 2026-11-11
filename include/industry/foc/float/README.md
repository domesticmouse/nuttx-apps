# `include/industry/foc/float`

## Overview
Implements `include/industry/foc/float` source and header components (`foc_align.h`, `foc_angle.h`, `foc_cordic.h`, `foc_feedforward.h` and 6 more files) in the NuttX application tree.

## Interface
- [foc_align.h:struct foc_routine_align_cb_f32_s]
- [foc_align.h:struct foc_routine_align_cfg_f32_s]
- [foc_align.h:struct foc_routine_aling_final_f32_s]
- [foc_angle.h:struct foc_angle_in_f32_s]
- [foc_angle.h:struct foc_angle_out_f32_s]
- [foc_angle.h:struct foc_angle_ops_f32_s]
- [foc_angle.h:struct foc_angle_f32_s]
- [foc_angle.h:struct foc_openloop_cfg_f32_s]
- [foc_angle.h:struct foc_angle_onfo_cfg_f32_s]
- [foc_angle.h:struct foc_angle_osmo_cfg_f32_s]
- [foc_angle.h:struct foc_qenco_cfg_f32_s]
- [foc_angle.h:struct foc_hall_cfg_f32_s]
- [foc_angle.h:foc_angle_f32_t]
- [foc_angle.h:foc_angle_init_f32]
- [foc_angle.h:foc_angle_deinit_f32]
- [foc_angle.h:foc_angle_cfg_f32]
- [foc_angle.h:foc_angle_zero_f32]
- [foc_angle.h:foc_angle_dir_f32]

## Invariants
- [foc_angle.h:CONFIG_INDUSTRY_FOC_ANGLE_OPENLOOP]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_ANGLE_OPENLOOP`.
- [foc_angle.h:CONFIG_INDUSTRY_FOC_ANGLE_ONFO]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_ANGLE_ONFO`.
- [foc_angle.h:CONFIG_INDUSTRY_FOC_ANGLE_OSMO]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_ANGLE_OSMO`.
- [foc_angle.h:CONFIG_INDUSTRY_FOC_ANGLE_QENCO]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_ANGLE_QENCO`.
- [foc_angle.h:CONFIG_INDUSTRY_FOC_ANGLE_HALL]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_ANGLE_HALL`.
- [foc_cordic.h:CONFIG_INDUSTRY_FOC_CORDIC_DQSAT]: Conditional compilation gated by `CONFIG_INDUSTRY_FOC_CORDIC_DQSAT`.

## Side Effects
- None

## Verification
- Run: `make test`
