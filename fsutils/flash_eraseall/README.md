# Flash Bulk Erase Utility (`fsutils/flash_eraseall`)

## Overview
Provides the `flash_eraseall()` library function (`CONFIG_FSUTILS_FLASH_ERASEALL`) to bulk-erase an MTD flash block/character driver device via `MTDIOC_BULKERASE`.

## Interface
- `[flash_eraseall.c:flash_eraseall]`: Opens the specified MTD driver path and issues `MTDIOC_BULKERASE`.
- `[Kconfig:FSUTILS_FLASH_ERASEALL]`: Enables building the `flash_eraseall` utility function.

## Invariants
- `[Kconfig:FSUTILS_FLASH_ERASEALL]`: Requires `MTD` support enabled in Kconfig.

## Side Effects
- `[flash_eraseall.c:flash_eraseall]`: Opens the target driver path with `O_RDONLY`, executes `ioctl(fd, MTDIOC_BULKERASE, 0)` to bulk-erase the flash medium, and closes the file descriptor.

## Verification
- Run: `make test`
