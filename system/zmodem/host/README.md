# `system/zmodem/host`

## Overview
Implements `system/zmodem/host` source and header components (`crc16.c`, `crc32.c`, `debug.h`) in the NuttX application tree.

## Interface
- [debug.h:EXTRA_FMT]
- [debug.h:EXTRA_ARG]
- [crc16.c:crc16part]
- [crc16.c:crc16]
- [crc32.c:crc32part]
- [crc32.c:crc32]
- `nuttx`: [./nuttx/README.md](./nuttx/README.md) - Implements `system/zmodem/host/nuttx`: Continue CRC calculation on a part of the buffer.

## Invariants
- [debug.h:CONFIG_HAVE_FUNCTIONNAME]: Conditional compilation gated by `CONFIG_HAVE_FUNCTIONNAME`.

## Side Effects
- None

## Verification
- Run: `make test`
