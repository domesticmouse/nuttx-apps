# `system/xrcedds/include/ucdr`

## Overview
Implements `system/xrcedds/include/ucdr` source and header components (`config.h`) in the NuttX application tree.

## Interface
- [config.h:MICROCDR_VERSION_MAJOR]
- [config.h:MICROCDR_VERSION_MINOR]
- [config.h:MICROCDR_VERSION_MICRO]
- [config.h:MICROCDR_VERSION_STR]
- [config.h:UCDR_MACHINE_ENDIANNESS]

## Invariants
- [config.h:CONFIG_ENDIAN_BIG]: Conditional compilation gated by `CONFIG_ENDIAN_BIG`.

## Side Effects
- None

## Verification
- Run: `make test`
