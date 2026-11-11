# `graphics/twm4nx/apps`

## Overview
Provides Touchscreen (`graphics/twm4nx/apps`). Enable support for the touchscreen calibration display.

## Interface
- [Kconfig:CONFIG_TWM4NX_CALIBRATION]
- [Kconfig:CONFIG_TW4NX_STARTUP_CALIB]
- [Kconfig:CONFIG_TWM4NX_NXTERM]
- [Kconfig:CONFIG_TWM4NX_CLOCK]
- [cclock.cxx:struct SClock]
- [cclock.cxx:struct std]
- [cnxterm.cxx:struct SNxTerm]

## Invariants
- [Kconfig:CONFIG_TWM4NX_CALIBRATION]: Build and feature compilation gated by `CONFIG_TWM4NX_CALIBRATION`.
- [Kconfig:CONFIG_TW4NX_STARTUP_CALIB]: Build and feature compilation gated by `CONFIG_TW4NX_STARTUP_CALIB`.
- [Kconfig:depends on TWM4NX_TOUCHSCREEN]: Requires Kconfig dependency condition `TWM4NX_TOUCHSCREEN`.
- [Kconfig:depends on NXTERM && NSH_LIBRARY]: Requires Kconfig dependency condition `NXTERM && NSH_LIBRARY`.
- [ccalibration.cxx:DEBUGASSERT]: Enforces `DEBUGASSERT(m_calthread == CALTHREAD_TERMINATED)` precondition.
- [ccalibration.cxx:DEBUGASSERT]: Enforces `DEBUGASSERT(errcode == EINTR || errcode == ECANCELED)` precondition.

## Side Effects
- [ccalibration.cxx:open]: Performs VFS file or device descriptor I/O operations.
- [ccalibration.cxx:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [cclock.cxx:task_create]: Spawns child tasks, pthreads, or built-in applications.
- [cnxterm.cxx:unlink]: Performs VFS file or device descriptor I/O operations.
- [cnxterm.cxx:task_create]: Spawns child tasks, pthreads, or built-in applications.

## Verification
- Run: `make test`
