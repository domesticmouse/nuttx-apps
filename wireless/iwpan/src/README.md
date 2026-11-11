# `wireless/iwpan/src`

## Overview
Implements `wireless/iwpan/src` source and header components (`iwpan.c`) in the NuttX application tree.

## Interface
- [iwpan.c:struct iwpan_command_s]
- [iwpan.c:u]
- [iwpan.c:main]

## Invariants
- None

## Side Effects
- [iwpan.c:close]: Performs VFS file or device descriptor I/O operations.
- [iwpan.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [iwpan.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
