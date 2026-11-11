# NxScope Real-Time Data Logging (`logging/nxscope`)

## Overview
Implements the `nxscope` real-time multi-channel data streaming and diagnostic logging library (`CONFIG_LOGGING_NXSCOPE`), supporting typed scalar/vector/metadata sample channels, pluggable serial/UDP/dummy transport interfaces, and CRC-protected serial framing.

## Interface
- `[nxscope.c:nxscope_init]` / `[nxscope.c:nxscope_deinit]`: Initializes and tears down an `struct nxscope_s` instance, its channel descriptors, and stream/command buffers.
- `[nxscope.c:nxscope_lock]` / `[nxscope.c:nxscope_unlock]`: Acquires and releases the instance `pthread_mutex_t` lock.
- `[nxscope.c:nxscope_stream]` / `[nxscope.c:nxscope_recv]` / `[nxscope.c:nxscope_stream_start]`: Flushes accumulated stream frames, processes incoming control frames, and toggles streaming state.
- `[nxscope_chan.c:nxscope_chan_init]` / `[nxscope_chan.c:nxscope_chan_en]` / `[nxscope_chan.c:nxscope_chan_div]` / `[nxscope_chan.c:nxscope_chan_all_en]`: Configures channel data types, enable flags, and sample decimation dividers.
- `[nxscope_chan.c:nxscope_put_samples]` and typed helpers (`[nxscope_chan.c:nxscope_put_uint8]`, `[nxscope_chan.c:nxscope_put_float]`, `[nxscope_chan.c:nxscope_put_vfloat_m]`, etc.): Push scalar or vector samples and optional metadata into the active stream buffer.
- `[nxscope_iser.c:nxscope_ser_init]` / `[nxscope_iser.c:nxscope_ser_deinit]`, `[nxscope_iudp.c:nxscope_udp_init]` / `[nxscope_iudp.c:nxscope_udp_deinit]`, `[nxscope_idummy.c:nxscope_dummy_init]` / `[nxscope_idummy.c:nxscope_dummy_deinit]`: Serial, UDP, and dummy transport interface backends.
- `[nxscope_pser.c:nxscope_proto_ser_init]` / `[nxscope_pser.c:nxscope_proto_ser_deinit]`: Serial frame protocol handler (`SOF 0x55` + CRC-16/XMODEM).

## Invariants
- `[nxscope_chan.c:CONFIG_ENDIAN_BIG]`: Big-endian targets fail at compile time with `#error Big endian not tested`; sample vectors in stream buffers are always serialized in little-endian order (`[nxscope_chan.c:nxscope_put_vector]`).
- `[nxscope.c:nxscope_init]`: Requires `cfg->intf_cmd`, `cfg->proto_cmd`, `cfg->intf_stream`, and `cfg->proto_stream` to be non-NULL with `initialized == true` and valid `send`/`recv`/`frame_get`/`frame_final` ops, plus `cfg->streambuf_len > 0`, `cfg->channels > 0`, and `cfg->rxbuf_len > 0`.
- `[nxscope_chan.c:nxscope_chan_init]` and `[nxscope_chan.c:nxscope_chan_en]`: Channel index `ch` must be `< s->cmninfo.chmax`, and enabling a channel requires `s->chinfo[ch].type.s.dtype != NXSCOPE_TYPE_UNDEF`.
- `[nxscope_pser.c:nxscope_hdr_fill]`: Serial protocol frames start with `0x55` (`NXSCOPE_HDR_SOF`), store frame length in little-endian, and end with a big-endian CRC-16/XMODEM checksum.
- `[nxscope_iudp.c:nxscope_udp_send]`: Requires `priv->peer_valid` to have been set by a prior `recvfrom`, returning `-ENOTCONN` otherwise.

## Side Effects
- `[nxscope.c:nxscope_init]` and `[nxscope.c:nxscope_deinit]`: Allocate and free heap buffers (`streambuf`, `chinfo`, `cntr`, `rxbuf`, `txbuf`, `cribuf`, and backend `priv` structures) via `zalloc`/`free` and manage `pthread_mutex_t` locks.
- `[nxscope_iser.c:nxscope_ser_init]`, `[nxscope_iser.c:nxscope_ser_send]`, and `[nxscope_iser.c:nxscope_ser_recv]`: Open serial character devices, configure raw `termios` baudrate/flags (`tcgetattr`, `cfsetspeed`, `cfmakeraw`, `tcsetattr`), and read/write serial file descriptors.
- `[nxscope_iudp.c:nxscope_udp_init]`, `[nxscope_iudp.c:nxscope_udp_send]`, and `[nxscope_iudp.c:nxscope_udp_recv]`: Create, bind, configure (`fcntl` `O_NONBLOCK`), and send/receive datagrams on `AF_INET` UDP sockets.
- `[nxscope_idummy.c:nxscope_dummy_send]` and `[nxscope_idummy.c:nxscope_dummy_recv]`: Dump frame buffers via `lib_dumpbuffer`.

## Verification
- Run: `make test`
