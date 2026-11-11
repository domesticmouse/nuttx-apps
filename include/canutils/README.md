# `include/canutils`

## Overview
Implements `include/canutils`: Wrapper for CANIOC_SET_BITTIMING Input Parameter:

## Interface
- [canlib.h:canlib_setbaud]
- [canlib.h:canlib_getbaud]
- [canlib.h:canlib_setloopback]
- [canlib.h:canlib_getloopback]
- [canlib.h:canlib_setsilent]
- [canlib.h:canlib_getsilent]
- [obd.h:struct obd_dev_s]
- [obd.h:obd_init]
- [obd.h:obd_send_request]
- [obd.h:obd_wait_response]
- [obd.h:obd_decode_pid]
- [obd_frame.h:OBD_FRAME_TYPE]
- [obd_frame.h:OBD_SINGLE_FRAME]
- [obd_frame.h:OBD_FIRST_FRAME]
- [obd_frame.h:OBD_CONSEC_FRAME]
- [obd_frame.h:OBD_FLWCTRL_FRAME]
- `lely`: [./lely/README.md](./lely/README.md) - Implements `include/canutils/lely` source and header components (`config.h`) in the NuttX application tree.

## Invariants
- [obd.h:CONFIG_MULTIFRAME_SUPPORT]: Conditional compilation gated by `CONFIG_MULTIFRAME_SUPPORT`.

## Side Effects
- None

## Verification
- Run: `make test`
