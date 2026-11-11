# `canutils/candump`

## Overview
SocketCAN bus monitoring and logging utility (`candump`) supporting multiple CAN/CAN FD interfaces, ID/error filtering, timestamps, and ASCII log output.

## Interface
- [candump.c:candump_main]
- [Kconfig:CANUTILS_CANDUMP]
- [Kconfig:CANUTILS_CANDUMP_STACKSIZE]
- [Makefile:PROGNAME]

## Invariants
- [candump.c:MAXSOCK] and [candump.c:MAX_FILTER]: At most `16` CAN interfaces (`MAXSOCK`) and `30` filters (`MAX_FILTER`) per socket may be monitored simultaneously.
- [candump.c:candump_main]: Requires `argc > optind` and `optind != 0`.

## Side Effects
- [candump.c:candump_main]: Opens `PF_CAN` raw sockets (`socket(PF_CAN, SOCK_RAW, CAN_RAW)`), issues `SIOCGIFINDEX`/`SIOCGIFNAME` `ioctl` calls, configures `CAN_RAW_*` socket options, writes log files, and prints received CAN frames to `stdout`.

## Verification
- Run: `make test`
