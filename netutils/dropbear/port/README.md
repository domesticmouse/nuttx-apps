# `netutils/dropbear/port`

## Overview
Implements `netutils/dropbear/port` source and header components (`config.h`, `dropbear_chachapoly.c`, `dropbear_ltc_hmac_sha256.c`, `dropbear_utils.c` and 6 more files) in the NuttX application tree.

## Interface
- [dropbear_utils.h:dropbear_hex_encode]
- [dropbear_utils.h:dropbear_hex_decode]
- [dropbear_utils.h:dropbear_try_prepare_parent]
- [localoptions.h:DROPBEAR_TRACKING_MALLOC]
- [localoptions.h:ECDSA_PRIV_FILENAME]
- [localoptions.h:DROPBEAR_SVR_DROP_PRIVS]
- [localoptions.h:DROPBEAR_SVR_MULTIUSER]
- [localoptions.h:DROPBEAR_SVR_PASSWORD_AUTH]
- [localoptions.h:DROPBEAR_SVR_PUBKEY_AUTH]
- [localoptions.h:DROPBEAR_SVR_PUBKEY_OPTIONS]
- [localoptions.h:DROPBEAR_REEXEC]
- [localoptions.h:DROPBEAR_SMALL_CODE]
- [localoptions.h:DROPBEAR_USER_ALGO_LIST]
- [localoptions.h:DROPBEAR_X11FWD]
- [localoptions.h:DROPBEAR_SVR_AGENTFWD]
- [localoptions.h:DROPBEAR_SVR_LOCALTCPFWD]
- [nuttx_config.h:getuid]
- [nuttx_config.h:geteuid]

## Invariants
- [localoptions.h:CONFIG_SCHED_USER_IDENTITY]: Conditional compilation gated by `CONFIG_SCHED_USER_IDENTITY`.
- [nuttx_config.h:CONFIG_NETUTILS_DROPBEAR_SYSLOG]: Conditional compilation gated by `CONFIG_NETUTILS_DROPBEAR_SYSLOG`.
- [nuttx_config.h:CONFIG_NETUTILS_DROPBEAR_COMPRESSION]: Conditional compilation gated by `CONFIG_NETUTILS_DROPBEAR_COMPRESSION`.
- [nuttx_config.h:CONFIG_SCHED_USER_IDENTITY]: Conditional compilation gated by `CONFIG_SCHED_USER_IDENTITY`.
- [dropbear_ltc_hmac_sha256.c:static_assert]: Enforces `static_assert(sizeof(int) + sizeof(uint32_t) <= sizeof(hash_state)` precondition.
- [dropbear_utils.c:CONFIG_SCHED_USER_IDENTITY]: Conditional compilation gated by `CONFIG_SCHED_USER_IDENTITY`.

## Side Effects
- [dropbear_chachapoly.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [dropbear_chachapoly.c:open]: Performs VFS file or device descriptor I/O operations.
- [dropbear_ltc_hmac_sha256.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [dropbear_ltc_hmac_sha256.c:open]: Performs VFS file or device descriptor I/O operations.
- [dropbear_utils.c:mkdir]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
