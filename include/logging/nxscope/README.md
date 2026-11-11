# `include/logging/nxscope`

## Overview
Implements `include/logging/nxscope`: Initialize nxscope channel Input Parameters:

## Interface
- [nxscope.h:enum nxscope_hdr_id_e]
- [nxscope.h:enum nxscope_info_flags_e]
- [nxscope.h:enum nxscope_stream_flags_s]
- [nxscope.h:enum nxscope_set_frame_req_s]
- [nxscope.h:union nxscope_chinfo_type_u]
- [nxscope.h:struct nxscope_sample_s]
- [nxscope.h:struct nxscope_stream_s]
- [nxscope.h:struct nxscope_callbacks_s]
- [nxscope.h:struct nxscope_cfg_s]
- [nxscope.h:struct nxscope_s]
- [nxscope.h:end_packed_struct]
- [nxscope.h:nxscope_init]
- [nxscope.h:nxscope_deinit]
- [nxscope.h:nxscope_lock]
- [nxscope.h:nxscope_unlock]
- [nxscope.h:nxscope_stream]
- [nxscope.h:nxscope_recv]
- [nxscope.h:nxscope_stream_start]

## Invariants
- [nxscope.h:CONFIG_LOGGING_NXSCOPE_CRICHANNELS]: Conditional compilation gated by `CONFIG_LOGGING_NXSCOPE_CRICHANNELS`.
- [nxscope.h:CONFIG_LOGGING_NXSCOPE_DIVIDER]: Conditional compilation gated by `CONFIG_LOGGING_NXSCOPE_DIVIDER`.
- [nxscope_chan.h:CONFIG_LOGGING_NXSCOPE_USERTYPES]: Conditional compilation gated by `CONFIG_LOGGING_NXSCOPE_USERTYPES`.
- [nxscope_chan.h:CONFIG_LOGGING_NXSCOPE_DIVIDER]: Conditional compilation gated by `CONFIG_LOGGING_NXSCOPE_DIVIDER`.
- [nxscope_intf.h:CONFIG_LOGGING_NXSCOPE_INTF_SERIAL]: Conditional compilation gated by `CONFIG_LOGGING_NXSCOPE_INTF_SERIAL`.
- [nxscope_intf.h:CONFIG_LOGGING_NXSCOPE_INTF_DUMMY]: Conditional compilation gated by `CONFIG_LOGGING_NXSCOPE_INTF_DUMMY`.

## Side Effects
- None

## Verification
- Run: `make test`
