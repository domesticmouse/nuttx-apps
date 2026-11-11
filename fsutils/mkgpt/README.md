# GUID Partition Table Formatter (`fsutils/mkgpt`)

## Overview
Implements the `mkgpt` command-line utility (`CONFIG_FSUTILS_MKGPT`) to create, verify, and inspect GUID Partition Table (GPT) layouts and protective MBR headers on block devices or disk image files.

## Interface
- `[mkgpt.c:main]`: CLI entry point (`mkgpt`) parsing partition specifications and writing/verifying GPT headers and entries.
- `[mkgpt.c:add_ptn]`: Appends a partition entry with computed LBA bounds and UUIDs to the in-memory GPT table.
- `[Kconfig:FSUTILS_MKGPT]`, `[Makefile:PROGNAME]`: Build configuration and application name (`mkgpt`).

## Invariants
- `[mkgpt.c:main]` and `[mkgpt.c:parse_ptn]`: Total disk/file size and each partition size must be non-zero multiples of 512 bytes.
- `[mkgpt.c:add_ptn]`: Partition `first_lba >= 34`, `last_lba <= hdr->last_lba` (`sz - 33`), and `entries_count <= EFI_ENTRIES` (`128`).
- `[mkgpt.c:verify_gpt_pratition]`: Valid GPT verification requires protective/hybrid MBR type `0xee` or `0x00`, MBR signature `0x55 0xaa`, `EFI_MAGIC` (`"EFI PART"`), valid header and entry CRC32 checksums, and `header_lba == 1`.

## Side Effects
- `[mkgpt.c:main]`: Opens the target block device/file `O_RDWR`, reads or writes the protective MBR, primary GPT header/entries, and secondary GPT header/entries at the end of the disk, and calls `fsync`.
- `[mkgpt.c:get_uuid]`: Generates random partition UUIDs via `arc4random_buf`.
- `[mkgpt.c:show]` and `[mkgpt.c:main]`: Read `@<file>` partition definition files, print partition summaries to `stderr`, and dump buffers via `lib_dumpbuffer` on verification errors.

## Verification
- Run: `make test`
