# `include/industry`

## Overview
Implements `include/industry` source and header components (`abnt_codi.h`) in the NuttX application tree.

## Interface
- [abnt_codi.h:struct abnt_codi_proto_s]
- [abnt_codi.h:abnt_codi_checksum]
- [abnt_codi.h:abnt_codi_parse]
- [abnt_codi.h:END_ACT_DEM_MASK]
- [abnt_codi.h:BILL_INDICADOR]
- [abnt_codi.h:REACT_INTERVAL]
- [abnt_codi.h:REACT_CAP_PULSE]
- [abnt_codi.h:REACT_IND_PULSE]
- [abnt_codi.h:SEGMENT_MASK]
- [abnt_codi.h:SEGMENT_PEEK]
- [abnt_codi.h:SEGMENT_OUT_PEEK]
- [abnt_codi.h:SEGMENT_RESERVED]
- [abnt_codi.h:CHARGES_MASK]
- [abnt_codi.h:CHARGES_BLUE]
- [abnt_codi.h:CHARGES_GREEN]
- [abnt_codi.h:CHARGES_IRRIGATORS]
- `foc`: [./foc/README.md](./foc/README.md) - Implements `include/industry/foc` source and header components (`foc_common.h`, `foc_log.h`, `foc_utils.h`) in the NuttX application tree.

## Invariants
- None

## Side Effects
- None

## Verification
- Run: `make test`
