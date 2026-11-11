# NxBoot Flash & Partition Loader (`boot/nxboot/loader`)

## Overview
Implements the core firmware slot validation, update, revert, confirmation, RAM-copy, and MTD flash partition access routines for the NuttX Bootloader (`nxboot`).

## Interface
- `[boot.c:nxboot_perform_update]`: Validates primary, secondary, and tertiary flash slots and executes firmware upgrade or revert operations.
- `[boot.c:nxboot_get_state]`: Inspects flash slots and returns the current `enum nxboot_state`.
- `[boot.c:nxboot_get_confirm]` / `[boot.c:nxboot_confirm]`: Queries whether the running primary image is confirmed and writes confirmation state to flash.
- `[boot.c:nxboot_open_update_partition]`: Opens the configured update slot device for writing new firmware images.
- `[boot.c:nxboot_ramcopy]`: Copies a validated primary slot image into RAM prior to boot.
- `[flash.c:flash_partition_open]` / `[flash.c:flash_partition_close]` / `[flash.c:flash_partition_flush]` / `[flash.c:flash_partition_read]` / `[flash.c:flash_partition_write]` / `[flash.c:flash_partition_erase]` / `[flash.c:flash_partition_erase_first_sector]` / `[flash.c:flash_partition_info]`: Low-level MTD/character device flash partition helpers declared in `[flash.h:flash_partition_info]`.

## Invariants
- `[boot.c:validate_image_header]`: Requires a valid image header to have `magic == NXBOOT_HEADER_MAGIC` or `(magic & NXBOOT_HEADER_MAGIC_INT_MASK) == NXBOOT_HEADER_MAGIC_INT` (`IS_INTERNAL_MAGIC`) and `identifier == CONFIG_NXBOOT_PLATFORM_IDENTIFIER`.
- `[boot.c:calculate_crc]` and `[boot.c:validate_image]`: Require the inverted CRC32 (`~crc32part` over header bytes after the `crc` field plus image payload) to equal `header.crc`.
- `[flash.c:flash_partition_write]`, `[flash.c:flash_partition_read]`, and `[boot.c:copy_partition]`: Require `count + off <= geometry.erasesize * geometry.neraseblocks` and `header.size + header.header_size <= info_where.size`.
- `[boot.c:nxboot_get_state]` and `[boot.c:nxboot_get_confirm]`: Treat the primary slot as confirmed if `primary_header.magic == NXBOOT_HEADER_MAGIC`, or if `IS_INTERNAL_MAGIC(primary_header.magic)` and the recovery slot indicated by `primary_header.magic & NXBOOT_RECOVERY_PTR_MASK` has a matching `crc`.

## Side Effects
- `[flash.c:flash_partition_open]`, `[flash.c:flash_partition_write]`, `[flash.c:flash_partition_read]`, `[flash.c:flash_partition_erase]`, and `[flash.c:flash_partition_erase_first_sector]`: Open, read, write, seek, flush (`fsync`), query geometry (`MTDIOC_GEOMETRY`), and erase (`MTDIOC_BULKERASE`, `MTDIOC_ERASESECTORS`) MTD flash partitions at `CONFIG_NXBOOT_PRIMARY_SLOT_PATH`, `CONFIG_NXBOOT_SECONDARY_SLOT_PATH`, and `CONFIG_NXBOOT_TERTIARY_SLOT_PATH`.
- `[boot.c:copy_partition]` and `[boot.c:perform_update]`: Copy firmware images between flash slots, update header magic between `NXBOOT_HEADER_MAGIC` and `NXBOOT_HEADER_MAGIC_INT`, and erase the first sector of the update slot after completion.
- `[boot.c:nxboot_ramcopy]`: Reads the primary slot image and copies it into memory at `CONFIG_NXBOOT_RAMSTART` when `CONFIG_NXBOOT_COPY_TO_RAM` is enabled.

## Verification
- Run: `make test`
