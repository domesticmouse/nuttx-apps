# SmartFS Filesystem Formatter (`fsutils/mksmartfs`)

## Overview
Implements the `mksmartfs()` and `issmartfs()` library functions (`CONFIG_FSUTILS_MKSMARTFS`) for checking and formatting SmartFS flash filesystems on NuttX SMART block devices.

## Interface
- `[mksmartfs.c:issmartfs]`: Checks whether the SMART block device at `pathname` is already formatted with SmartFS.
- `[mksmartfs.c:mksmartfs]`: Performs a low-level SMART format and allocates root directory logical sector(s) on `pathname`.
- `[Kconfig:FSUTILS_MKSMARTFS]`: Enables building the SmartFS formatting utilities.

## Invariants
- `[Kconfig:FSUTILS_MKSMARTFS]`: Depends on `FS_SMARTFS && !DISABLE_PSEUDOFS_OPERATIONS` and selects `BCH`.
- `[mksmartfs.c:issmartfs]`: Requires `SMART_FMT_ISFORMATTED` to be set in the `BIOC_GETFORMAT` result; otherwise sets `errno = EFTYPE`.
- `[mksmartfs.c:mksmartfs]`: Requires `BIOC_ALLOCSECT` to return the exact requested root directory logical sector number (`SMARTFS_ROOT_DIR_SECTOR + x`).

## Side Effects
- `[mksmartfs.c:issmartfs]`: Opens the device with `O_RDONLY` and invokes `ioctl(fd, BIOC_GETFORMAT, ...)`.
- `[mksmartfs.c:mksmartfs]`: Opens the device with `O_RDWR`, invokes `BIOC_LLFORMAT`, `BIOC_GETFORMAT`, `BIOC_ALLOCSECT`, and `BIOC_WRITESECT` `ioctl` calls to format the medium and write root directory sectors, and sets `errno` on failure.

## Verification
- Run: `make test`
