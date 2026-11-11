# Bootloaders (`boot`)

## Overview
Groups bootloader applications and firmware update utilities for NuttX targets.

## Subdirectories & Boundaries
- `miniboot`: [./miniboot/README.md](./miniboot/README.md) - Minimal direct-boot application invoking `BOARDIOC_BOOT_IMAGE` on a configured slot path.
- `nxboot`: [./nxboot/README.md](./nxboot/README.md) - Full-featured A/B/recovery bootloader with CRC32 verification, rollback protection, and host image generation tools.
