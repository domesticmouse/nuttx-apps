# `system/uorb/test`

## Overview
Implements `system/uorb/test` source and header components (`utility.c`, `utility.h`) in the NuttX application tree.

## Interface
- [utility.h:struct orb_test_s]
- [utility.h:struct orb_test_medium_s]
- [utility.h:struct orb_test_large_s]
- [utility.h:test_note]
- [utility.h:test_fail]
- [utility.c:test_note]
- [utility.c:test_fail]

## Invariants
- [utility.c:CONFIG_UORB_FORMAT]: Conditional compilation gated by `CONFIG_UORB_FORMAT`.

## Side Effects
- [utility.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
