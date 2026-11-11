# `canutils/cansend`

## Overview
SocketCAN command-line utility (`cansend`) for transmitting single CAN 2.0 or CAN FD frames onto a named CAN network interface.

## Interface
- [cansend.c:cansend_main]
- [Kconfig:CANUTILS_CANSEND]
- [Kconfig:CANUTILS_CANSEND_STACKSIZE]
- [Makefile:PROGNAME]

## Invariants
- [cansend.c:cansend_main]: Requires `argc == 3` (`<can-interface> <can-frame>`), interface name length `< IFNAMSIZ`, and `SIOCGIFMTU >= CANFD_MTU` when sending CAN FD frames.

## Side Effects
- [cansend.c:cansend_main]: Opens a `PF_CAN` raw socket, queries `SIOCGIFINDEX` and `SIOCGIFMTU` via `ioctl`, disables `CAN_RAW_FILTER`, binds the socket, and writes the parsed CAN frame.

## Verification
- Run: `make test`
