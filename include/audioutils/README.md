# `include/audioutils`

## Overview
Implements `include/audioutils` source and header components (`fmsynth.h`, `fmsynth_eg.h`, `fmsynth_op.h`, `mml_parser.h` and 1 more files) in the NuttX application tree.

## Interface
- [fmsynth.h:struct fmsynth_sound_s]
- [fmsynth.h:fmsynth_sound_t]
- [fmsynth.h:fmsynth_initialize]
- [fmsynth.h:fmsynthsnd_create]
- [fmsynth.h:create_fmsynthsnd]
- [fmsynth.h:fmsynthsnd_stop]
- [fmsynth.h:fmsynthsnd_delete]
- [fmsynth.h:fmsynthsnd_set_operator]
- [fmsynth.h:fmsynthsnd_set_soundfreq]
- [fmsynth.h:fmsynthsnd_set_volume]
- [fmsynth.h:fmsynthsnd_add_subsound]
- [fmsynth.h:fmsynth_rendering]
- [fmsynth.h:FMSYNTH_MAX_VOLUME]
- [fmsynth_eg.h:struct fmsynth_eglevel_s]
- [fmsynth_eg.h:struct fmsynth_eglevels_s]
- [fmsynth_eg.h:struct fmsynth_egparam_s]
- [fmsynth_eg.h:struct fmsynth_eg_s]
- [fmsynth_eg.h:fmsynth_eglevels_t]

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
