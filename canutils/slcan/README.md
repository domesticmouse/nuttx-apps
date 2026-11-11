# `canutils/slcan`

## Overview
Serial Line CAN (`slcan`) bridge daemon (`CONFIG_CANUTILS_SLCAN`) translating LAWICEL ASCII serial commands on a UART device to and from a SocketCAN interface.

## Interface
- [slcan.c:slcan_main]
- [slcan.h:SLLIN_START_TOUT]
- [Kconfig:CANUTILS_SLCAN]
- [Kconfig:SLCAN_TRACE]
- [Makefile:PROGNAME]

## Invariants
- [Kconfig:CANUTILS_SLCAN]: Depends on `NET_CAN && CAN_FD`.
- [slcan.c:slcan_main]: Requires `argc == 4` (`<uart device> <can interface> <mode>`) and `mode` in `0..8`.

## Side Effects
- [slcan.c:slcan_main]: Opens the UART device (`O_RDWR | O_NOCTTY`), configures raw 115200 8N1 `termios`, opens a `PF_CAN` raw socket, sets `IFF_UP` via `SIOCSIFFLAGS` `ioctl`, and relays frames between the serial line and SocketCAN.

## Verification
- Run: `make test`
