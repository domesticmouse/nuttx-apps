# `canutils/libcanutils`

## Overview
Shared SocketCAN frame string parsing, formatting, and terminal color library (`CONFIG_CANUTILS_LIBCANUTILS`) used by `candump` and `cansend`.

## Interface
- [lib.h:asc2nibble]
- [lib.h:hexstring2data]
- [lib.h:parse_canframe]
- [lib.h:fprint_canframe]
- [lib.h:sprint_canframe]
- [lib.h:fprint_long_canframe]
- [lib.h:sprint_long_canframe]
- [lib.h:snprintf_can_error_frame]
- [Kconfig:CANUTILS_LIBCANUTILS]

## Invariants
- [lib.c:CANID_DELIM] and [lib.c:parse_canframe]: Valid CAN frame strings must contain `'#'` at index 3 (standard ID) or 8 (extended ID), with payload length `<= CAN_MAX_DLEN` (8) or `CANFD_MAX_DLEN` (64).
- [lib.c:sprint_canframe] and [lib.c:sprint_long_canframe]: Require `view <= 0x7f` and `view <= 0x1ff` respectively.

## Side Effects
- [lib.c:fprint_canframe] and [lib.c:fprint_long_canframe]: Format and write human-readable CAN frame representations to `FILE *stream`.

## Verification
- Run: `make test`
