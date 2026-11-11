# FAT Filesystem Formatter (`fsutils/mkfatfs`)

## Overview
Implements the `mkfatfs()` library utility (`CONFIG_FSUTILS_MKFATFS`) to format a NuttX block device with a FAT12, FAT16, or FAT32 filesystem.

## Interface
- `[mkfatfs.c:mkfatfs]`: Formats the block device at `pathname` according to caller-supplied `struct fat_format_s` parameters.
- `[configfat.c:mkfatfs_configfatfs]`: Computes optimal cluster size, FAT type (FAT12/16/32), FAT table size, and sector layout.
- `[writefat.c:mkfatfs_writefatfs]`: Writes the Master Boot Record (MBR)/Volume Boot Record (VBR), FSINFO sector, backup boot sector, FAT tables, and root directory sectors to the block device.
- `[mkfatfs.h:fat_var_s]`, `[fat32.h:FAT_PUTUINT16]`, `[fat32.h:FAT_PUTUINT32]`: Internal FAT formatting state structure and little-endian serialization macros.
- `[Kconfig:FSUTILS_MKFATFS]`, `[Kconfig:MKFATFS_BUFFER_ALIGNMENT]`: Build and sector buffer alignment configuration flags.

## Invariants
- `[mkfatfs.c:mkfatfs_getgeometry]`: Block device must report `geo_available` and `geo_writeenabled` via `BIOC_GEOMETRY`, `fmt->ff_nsectors <= geometry.geo_nsectors`, and hardware sector size in `{512, 1024, 2048, 4096}` bytes.
- `[mkfatfs.c:mkfatfs]`: When `CONFIG_DEBUG_FEATURES` is enabled, requires `pathname != NULL`, `ff_nfats` in `1..4`, `ff_fattype` in `{0, 12, 16, 32}`, `ff_clustshift <= 7` or `0xff`, `ff_rootdirentries == 0` or in `16..32767`, and `ff_rsvdseccount == 0` or in `1..32767`.
- `[configfat.c:mkfatfs_tryfat12]`, `[configfat.c:mkfatfs_tryfat16]`, and `[configfat.c:mkfatfs_tryfat32]`: Enforce FAT12/FAT16/FAT32 cluster count boundaries (`FAT_MAXCLUST12`, `FAT_MINCLUST16`..`FAT_MAXCLUST16`, `FAT_MINCLUST32`..`FAT_MAXCLUST32`) and require at least 2 reserved sectors for FAT32.
- `[writefat.c:mkfatfs_devwrite]`: Requires sector index `0 <= sector < fmt->ff_nsectors`.

## Side Effects
- `[mkfatfs.c:mkfatfs]` and `[writefat.c:mkfatfs_writefatfs]`: Open the target block device with `O_RDWR`, query geometry via `BIOC_GEOMETRY` `ioctl`, allocate sector buffers via `malloc`/`memalign`, and overwrite boot, FAT, and root directory sectors on the block device.
- `[mkfatfs.c:mkfatfs]` and `[configfat.c:mkfatfs_configfatfs]`: Mutate caller-passed `struct fat_format_s` fields (`ff_nsectors`, `ff_clustshift`, `ff_rsvdseccount`, `ff_rootdirentries`, `ff_backupboot`, `ff_fattype`) and set `errno` on failure.
- `[mkfatfs.c:fat_systime2fattime]`: Queries the system clock via `clock_gettime(CLOCK_REALTIME)` when `CONFIG_FS_FATTIME` is enabled.

## Verification
- Run: `make test`
