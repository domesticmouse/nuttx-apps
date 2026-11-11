# MikroElektronika STM32F4 Platform Config Data (`platform/mikroe-stm32f4`)

## Overview
Implements board-specific persistent configuration storage (`platform_setconfig` and `platform_getconfig`) for the MikroElektronika STM32F4 board (`ARCH_BOARD_MIKROE_STM32F4`), supporting `/dev/config` partition `ioctl` storage, filesystem file storage, or read-only ROM touchscreen calibration data.

## Interface
- `[mikroe_configdata.c:platform_setconfig]`: Saves platform configuration data identified by `(id, instance)` from caller buffer `configdata`.
- `[mikroe_configdata.c:platform_getconfig]`: Retrieves platform configuration data identified by `(id, instance)` into caller buffer `configdata`.
- `[Kconfig:CONFIG_MIKROE_STM32F4_CONFIGDATA_PART]`, `[Kconfig:CONFIG_MIKROE_STM32F4_CONFIGDATA_FS]`, `[Kconfig:CONFIG_MIKROE_STM32F4_CONFIGDATA_ROM]`, `[Kconfig:CONFIG_MIKROE_STM32F4_CONFIGDATA_FILENAME]`: Storage backend selection and file path configuration symbols.

## Invariants
- `[Kconfig:ARCH_BOARD_MIKROE_STM32F4]`: Options are gated on `ARCH_BOARD_MIKROE_STM32F4` and `PLATFORM_CONFIGDATA`.
- `[mikroe_configdata.c:platform_setconfig]`: When `CONFIG_MIKROE_STM32F4_CONFIGDATA_PART` is not enabled, only `id == CONFIGDATA_TSCALIBRATION` is supported; other IDs set `errno = ENOSYS` and return `-1`.
- `[mikroe_configdata.c:platform_getconfig]`: Under `CONFIG_MIKROE_STM32F4_CONFIGDATA_FS`, total bytes read from the file must equal `sizeof(saved_id) + sizeof(saved_instance) + datalen`; otherwise sets `errno = EINVAL` and returns `-1`.

## Side Effects
- `[mikroe_configdata.c:platform_setconfig]`: Opens `/dev/config` and issues `CFGDIOC_SETCONFIG` `ioctl` (when `CONFIG_MIKROE_STM32F4_CONFIGDATA_PART`), or opens/writes `CONFIG_MIKROE_STM32F4_CONFIGDATA_FILENAME` via `fopen`/`fwrite`/`fclose` (when `CONFIG_MIKROE_STM32F4_CONFIGDATA_FS`), setting `errno` on failure.
- `[mikroe_configdata.c:platform_getconfig]`: Opens `/dev/config` and issues `CFGDIOC_GETCONFIG` `ioctl`, reads `CONFIG_MIKROE_STM32F4_CONFIGDATA_FILENAME`, or copies static `touch_cal_data` via `memcpy`, setting `errno` on failure.

## Verification
- Run: `make test`
