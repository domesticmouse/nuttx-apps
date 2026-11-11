# `industry/foc/float`

## Overview
Implements `industry/foc/float`: Initialize the open-loop FOC angle handler (float32) Input Parameter:

## Interface
- [foc_align.c:enum foc_align_run_stage_e]
- [foc_align.c:struct foc_align_f32_s]
- [foc_align.c:foc_routine_align_init_f32]
- [foc_align.c:foc_routine_align_deinit_f32]
- [foc_align.c:foc_routine_align_cfg_f32]
- [foc_align.c:foc_routine_align_run_f32]
- [foc_align.c:foc_routine_align_final_f32]
- [foc_align.c:foc_align_dir_run_f32]
- [foc_ang_hall.c:struct foc_hall_f32_s]
- [foc_ang_onfo.c:struct foc_ang_onfo_f32_s]
- [foc_ang_openloop.c:struct foc_openloop_f32_s]
- [foc_ang_osmo.c:struct foc_ang_osmo_f32_s]
- [foc_ang_qenco.c:struct foc_qenco_f32_s]
- [foc_angle.c:foc_angle_init_f32]
- [foc_angle.c:foc_angle_deinit_f32]
- [foc_angle.c:foc_angle_cfg_f32]
- [foc_angle.c:foc_angle_zero_f32]
- [foc_angle.c:foc_angle_dir_f32]

## Invariants
- [foc_align.c:DEBUGASSERT]: Enforces `DEBUGASSERT(align)` precondition.
- [foc_align.c:DEBUGASSERT]: Enforces `DEBUGASSERT(0)` precondition.
- [foc_align.c:DEBUGASSERT]: Enforces `DEBUGASSERT(r)` precondition.
- [foc_align.c:DEBUGASSERT]: Enforces `DEBUGASSERT(cfg)` precondition.
- [foc_align.c:DEBUGASSERT]: Enforces `DEBUGASSERT(r->data)` precondition.
- [foc_align.c:DEBUGASSERT]: Enforces `DEBUGASSERT(in)` precondition.

## Side Effects
- [foc_align.c:zalloc]: Allocates or releases dynamic heap memory.
- [foc_ang_hall.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [foc_ang_hall.c:close]: Performs VFS file or device descriptor I/O operations.
- [foc_ang_hall.c:zalloc]: Allocates or releases dynamic heap memory.
- [foc_ang_onfo.c:zalloc]: Allocates or releases dynamic heap memory.
- [foc_ang_openloop.c:zalloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
