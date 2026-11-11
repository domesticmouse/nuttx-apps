# `graphics/nxwm/src`

## Overview
Implements `graphics/nxwm/src` source and header components (`capplicationwindow.cxx`, `ccalibration.cxx`, `cfullscreenwindow.cxx`, `chexcalculator.cxx` and 8 more files) in the NuttX application tree.

## Interface
- [chexcalculator.cxx:enum EKeyType]
- [chexcalculator.cxx:struct SKeyDesc]
- [cnxterm.cxx:struct SNxTerm]
- [nxwm_main.cxx:struct SNxWmTest]
- [nxwm_main.cxx:struct NxWM]
- [nxwm_main.cxx:main]

## Invariants
- [capplicationwindow.cxx:CONFIG_NXWM_STOP_BITMAP]: Conditional compilation gated by `CONFIG_NXWM_STOP_BITMAP`.
- [capplicationwindow.cxx:CONFIG_NXWM_MINIMIZE_BITMAP]: Conditional compilation gated by `CONFIG_NXWM_MINIMIZE_BITMAP`.
- [capplicationwindow.cxx:CONFIG_NXWM_DISABLE_MINIMIZE]: Conditional compilation gated by `CONFIG_NXWM_DISABLE_MINIMIZE`.
- [ccalibration.cxx:CONFIG_NXWM_TOUCHSCREEN_CONFIGDATA]: Conditional compilation gated by `CONFIG_NXWM_TOUCHSCREEN_CONFIGDATA`.
- [ccalibration.cxx:CONFIG_NX]: Conditional compilation gated by `CONFIG_NX`.
- [ccalibration.cxx:CONFIG_DEBUG_INPUT]: Conditional compilation gated by `CONFIG_DEBUG_INPUT`.

## Side Effects
- [capplicationwindow.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [ccalibration.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [ccalibration.cxx:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [cfullscreenwindow.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [chexcalculator.cxx:close]: Performs VFS file or device descriptor I/O operations.
- [ckeyboard.cxx:close]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
