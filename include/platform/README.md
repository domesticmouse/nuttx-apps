# `include/platform`

## Overview
Implements `include/platform`: Save platform-specific configuration data Input Parameter:

## Interface
- [configdata.h:enum config_data_e]
- [configdata.h:platform_setconfig]
- [configdata.h:platform_getconfig]

## Invariants
- [configdata.h:CONFIG_PLATFORM_CONFIGDATA]: Conditional compilation gated by `CONFIG_PLATFORM_CONFIGDATA`.

## Side Effects
- None

## Verification
- Run: `make test`
