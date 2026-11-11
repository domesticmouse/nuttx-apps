# FM Synthesizer Library (`audioutils/fmsynth`)

## Overview
Implements a software Frequency Modulation (FM) synthesizer library (`CONFIG_AUDIOUTILS_FMSYNTH_LIB`) providing envelope generators (`fmsynth_eg.c`), cascade/parallel/feedback phase-modulated operators (`fmsynth_op.c`), and multi-sound PCM buffer rendering (`fmsynth.c`).

## Interface
- `[fmsynth.c:fmsynth_initialize]`: Sets the global FM synthesizer sampling rate and phase wrap limit.
- `[fmsynth.c:fmsynthsnd_create]` / `[fmsynth.c:create_fmsynthsnd]` / `[fmsynth.c:fmsynthsnd_delete]`: Allocates, initializes, and destroys `fmsynth_sound_t` instances.
- `[fmsynth.c:fmsynthsnd_set_operator]` / `[fmsynth.c:fmsynthsnd_set_soundfreq]` / `[fmsynth.c:fmsynthsnd_set_volume]` / `[fmsynth.c:fmsynthsnd_add_subsound]` / `[fmsynth.c:fmsynthsnd_stop]`: Configures sound operators, fundamental frequency, volume, and sub-sounds.
- `[fmsynth.c:fmsynth_rendering]`: Renders synthesized 16-bit PCM frames into a sample buffer with optional per-tick callback invocation.
- `[fmsynth_eg.c:fmsyntheg_create]` / `[fmsynth_eg.c:create_fmsyntheg]` / `[fmsynth_eg.c:fmsyntheg_delete]` / `[fmsynth_eg.c:fmsyntheg_set_param]` / `[fmsynth_eg.c:fmsyntheg_start]` / `[fmsynth_eg.c:fmsyntheg_stop]` / `[fmsynth_eg.c:fmsyntheg_operate]`: ADSR envelope generator lifecycle and state machine routines.
- `[fmsynth_op.c:fmsynthop_set_samplerate]` / `[fmsynth_op.c:fmsynthop_create]` / `[fmsynth_op.c:create_fmsynthop]` / `[fmsynth_op.c:fmsynthop_delete]` / `[fmsynth_op.c:fmsynthop_select_opfunc]` / `[fmsynth_op.c:fmsynthop_set_envelope]` / `[fmsynth_op.c:fmsynthop_cascade_subop]` / `[fmsynth_op.c:fmsynthop_parallel_subop]` / `[fmsynth_op.c:fmsynthop_bind_feedback]` / `[fmsynth_op.c:fmsynthop_operate]`: Oscillator operator creation, waveform selection, topology wiring, and sample synthesis.
- `[Kconfig:CONFIG_AUDIOUTILS_FMSYNTH_LIB]`: Enables building the FM synthesizer library.

## Invariants
- `[fmsynth.c:WRAP_ROUND_TIME_SEC]`: Phase time wraps around to `0` upon reaching `max_phase_time` (`fs * 10`).
- `[fmsynth.c:fmsynthsnd_delete]` and `[fmsynth_op.c:fmsynthop_delete]`: Only call `free()` on instances where `own_allocate == 1`.
- `[fmsynth.c:fmsynthsnd_add_subsound]`: Returns `ERROR` if `top == NULL` or `sub == NULL`.
- `[fmsynth_eg.c:set_egparams]` and `[fmsynth_eg.c:fmsyntheg_set_param]`: Reject envelope parameters where `initval < -FMSYNTH_MAX_EGLEVEL`, `initval > FMSYNTH_MAX_EGLEVEL`, `period < 0`, or `fs <= 0`.
- `[fmsynth_op.c:fmsynthop_set_samplerate]` and `[fmsynth_op.c:fmsynthop_set_envelope]`: Require `fs >= 0`, `local_fs >= 0`, `op != NULL`, and `levels != NULL`.

## Side Effects
- `[fmsynth.c:fmsynth_initialize]` and `[fmsynth_op.c:fmsynthop_set_samplerate]`: Mutate file-scope static variables `max_phase_time` and `local_fs`.
- `[fmsynth.c:fmsynthsnd_create]`, `[fmsynth_eg.c:fmsyntheg_create]`, and `[fmsynth_op.c:fmsynthop_create]`: Allocate heap memory via `malloc` (freed by their respective `*_delete` functions).
- `[fmsynth.c:fmsynth_rendering]`: Writes synthesized PCM samples into caller-provided `samples` buffer and invokes callback `cb(cbarg)`.

## Verification
- Run: `make test`
