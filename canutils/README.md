# `canutils`

## Overview
Groups CAN Utilities (`canutils`) components and utilities for NuttX.

## Subdirectories & Boundaries
- `candump`: [./candump/README.md](./candump/README.md) - SocketCAN bus monitoring and logging utility (`candump`) supporting multiple CAN/CAN FD interfaces, ID/error filtering, timestamps, and ASCII log output.
- `canlib`: [./canlib/README.md](./canlib/README.md) - Provides CAN utility library (`canutils/canlib`). Enable the CAN utility library
- `cansend`: [./cansend/README.md](./cansend/README.md) - SocketCAN command-line utility (`cansend`) for transmitting single CAN 2.0 or CAN FD frames onto a named CAN network interface.
- `libcanutils`: [./libcanutils/README.md](./libcanutils/README.md) - Shared SocketCAN frame string parsing, formatting, and terminal color library (`CONFIG_CANUTILS_LIBCANUTILS`) used by `candump` and `cansend`.
- `libobd2`: [./libobd2/README.md](./libobd2/README.md) - On-Board Diagnostics II (OBD-II) PID request, response, and decoding library (`CONFIG_CANUTILS_LIBOBD2`) over NuttX CAN character driver devices.
- `slcan`: [./slcan/README.md](./slcan/README.md) - Serial Line CAN (`slcan`) bridge daemon (`CONFIG_CANUTILS_SLCAN`) translating LAWICEL ASCII serial commands on a UART device to and from a SocketCAN interface.
