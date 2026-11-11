# `canutils/libobd2`

## Overview
On-Board Diagnostics II (OBD-II) PID request, response, and decoding library (`CONFIG_CANUTILS_LIBOBD2`) over NuttX CAN character driver devices.

## Interface
- [obd2.c:obd_init]
- [obd_sendrequest.c:obd_sendrequest]
- [obd_waitresponse.c:obd_waitresponse]
- [obd_decodepid.c:obd_decodepid]
- [Kconfig:CANUTILS_LIBOBD2]

## Invariants
- [Kconfig:CANUTILS_LIBOBD2]: Depends on `CAN`.
- [obd_waitresponse.c:obd_waitresponse]: Requires received CAN message ID to match `0x7e8` (or `0x7e8 | 8` extended), single-frame length `ch_data[0] == 4`, and response mode `ch_data[1] == (opmode + 0x40)`.

## Side Effects
- [obd2.c:obd_init]: Allocates `struct obd_dev_s` via `malloc` and opens the CAN character device (`O_RDWR`).
- [obd_sendrequest.c:obd_sendrequest] and [obd_waitresponse.c:obd_waitresponse]: Write 8-byte CAN request frames (ID `0x7df`) to `dev->can_fd` and read response frames into `dev->can_rxmsg`.
- [obd_decodepid.c:obd_decodepid]: Allocates a string buffer via `malloc` and formats the decoded PID value.

## Verification
- Run: `make test`
