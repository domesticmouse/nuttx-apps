# `system/settings`

## Overview
Provides Settings Functions (`system/settings`). The settings storage can be used to store and retrieve various configurable parameters. This storage is a RAM-based map (for fast access)

## Interface
- [Kconfig:CONFIG_SYSTEM_SETTINGS]
- [Kconfig:CONFIG_SYSTEM_SETTINGS_MAP_SIZE]
- [Kconfig:CONFIG_SYSTEM_SETTINGS_KEY_SIZE]
- [Kconfig:CONFIG_SYSTEM_SETTINGS_VALUE_SIZE]
- [storage.h:load_text]
- [storage.h:save_text]
- [storage.h:load_bin]
- [storage.h:save_bin]
- [storage.h:load_eeprom]
- [storage.h:save_eeprom]
- [settings.c:g_settings]
- [settings.c:settings_init]
- [settings.c:settings_setstorage]
- [settings.c:settings_sync]
- [settings.c:settings_notify]
- [settings.c:settings_hash]
- [settings.c:settings_clear]
- [settings.c:settings_create]

## Invariants
- [Kconfig:CONFIG_SYSTEM_SETTINGS]: Build and feature compilation gated by `CONFIG_SYSTEM_SETTINGS`.
- [Kconfig:CONFIG_SYSTEM_SETTINGS_MAP_SIZE]: Build and feature compilation gated by `CONFIG_SYSTEM_SETTINGS_MAP_SIZE`.
- [settings.c:assert]: Enforces `assert(*setting == NULL)` precondition.
- [settings.c:assert]: Enforces `assert(setting)` precondition.
- [settings.c:assert]: Enforces `assert(len < CONFIG_SYSTEM_SETTINGS_VALUE_SIZE)` precondition.
- [settings.c:assert]: Enforces `assert(len < size)` precondition.

## Side Effects
- [storage_bin.c:open]: Performs VFS file or device descriptor I/O operations.
- [storage_bin.c:malloc]: Allocates or releases dynamic heap memory.
- [storage_text.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [storage_text.c:malloc]: Allocates or releases dynamic heap memory.
- [storage_text.c:fprintf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
