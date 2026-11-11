# NxBoot Public Header (`boot/nxboot/include`)

## Overview
Defines the public C API, slot constants, image header layout, state enumerations, and progress reporting types for the NuttX Bootloader (`nxboot`).

## Interface
- `[nxboot.h:NXBOOT_PRIMARY_SLOT_NUM]`, `[nxboot.h:NXBOOT_SECONDARY_SLOT_NUM]`, `[nxboot.h:NXBOOT_TERTIARY_SLOT_NUM]`: Flash slot index constants.
- `[nxboot.h:NXBOOT_HEADER_MAGIC]`, `[nxboot.h:NXBOOT_HEADER_MAGIC_INT]`, `[nxboot.h:NXBOOT_HEADER_MAGIC_INT_MASK]`, `[nxboot.h:NXBOOT_RECOVERY_PTR_MASK]`, `[nxboot.h:NXBOOT_HEADER_PRERELEASE_MAXLEN]`: Image header magic masks and size limits.
- `[nxboot.h:nxboot_img_header]`, `[nxboot.h:nxboot_img_version]`, `[nxboot.h:nxboot_hdr_version]`: Image header and semantic version structures.
- `[nxboot.h:nxboot_state]`, `[nxboot.h:nxboot_update_type]`, `[nxboot.h:progress_type_e]`, `[nxboot.h:progress_msg_e]`: Bootloader state, update action, and progress reporting enumerations.
- `[nxboot.h:nxboot_get_state]`, `[nxboot.h:nxboot_open_update_partition]`, `[nxboot.h:nxboot_get_confirm]`, `[nxboot.h:nxboot_confirm]`, `[nxboot.h:nxboot_perform_update]`, `[nxboot.h:nxboot_ramcopy]`, `[nxboot.h:nxboot_progress]`: Public bootloader control and progress functions.

## Invariants
- `[nxboot.h:CONFIG_NXBOOT_HEADER_SIZE]`: Compile-time `static_assert` requires `CONFIG_NXBOOT_HEADER_SIZE > sizeof(struct nxboot_img_header)`.

## Side Effects
- None

## Verification
- Run: `make test`
