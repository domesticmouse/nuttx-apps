# `system/zmodem/host/nuttx`

## Overview
Implements `system/zmodem/host/nuttx`: Continue CRC calculation on a part of the buffer.

## Interface
- [ascii.h:ASCII_NUL]
- [ascii.h:ASCII_SOH]
- [ascii.h:ASCII_STX]
- [ascii.h:ASCII_ETX]
- [ascii.h:ASCII_EOT]
- [ascii.h:ASCII_ENQ]
- [ascii.h:ASCII_ACK]
- [ascii.h:ASCII_BEL]
- [ascii.h:ASCII_BS]
- [ascii.h:ASCII_TAB]
- [ascii.h:ASCII_LF]
- [ascii.h:ASCII_VT]
- [ascii.h:ASCII_FF]
- [ascii.h:ASCII_CR]
- [ascii.h:ASCII_SO]
- [ascii.h:ASCII_SI]
- [config.h:zalloc]
- [crc16.h:crc16part]

## Invariants
- [compiler.h:CONFIG_AVR_HAS_MEMX_PTR]: Conditional compilation gated by `CONFIG_AVR_HAS_MEMX_PTR`.
- [compiler.h:CONFIG_EZ80_Z80MODE]: Conditional compilation gated by `CONFIG_EZ80_Z80MODE`.
- [config.h:sched_lock]: Synchronizes concurrent access across threads or critical sections.

## Side Effects
- [config.h:zalloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
