# `system/cle`

## Overview
Provides EMACS-like Command Line Editor (`system/cle`). Enable support for NuttX tiny EMACS-like command line editor.

## Interface
- [Kconfig:CONFIG_SYSTEM_CLE]
- [Kconfig:CONFIG_SYSTEM_COLOR_CLE]
- [Kconfig:CONFIG_SYSTEM_CLE_CMD_HISTORY]
- [Kconfig:CONFIG_SYSTEM_CLE_CMD_HISTORY_LINELEN]
- [cle.c:enum cle_key_e]
- [cle.c:struct cle_s]
- [cle.c:cle_fd]
- [cle.c:cle]

## Invariants
- [Kconfig:CONFIG_SYSTEM_CLE]: Build and feature compilation gated by `CONFIG_SYSTEM_CLE`.
- [Kconfig:CONFIG_SYSTEM_COLOR_CLE]: Build and feature compilation gated by `CONFIG_SYSTEM_COLOR_CLE`.
- [cle.c:CONFIG_SYSTEM_CLE_DEBUGLEVEL]: Conditional compilation gated by `CONFIG_SYSTEM_CLE_DEBUGLEVEL`.
- [cle.c:CONFIG_SYSTEM_COLOR_CLE]: Conditional compilation gated by `CONFIG_SYSTEM_COLOR_CLE`.
- [cle.c:CONFIG_SYSTEM_CLE_CMD_HISTORY]: Conditional compilation gated by `CONFIG_SYSTEM_CLE_CMD_HISTORY`.
- [cle.c:CONFIG_FILE_STREAM]: Conditional compilation gated by `CONFIG_FILE_STREAM`.

## Side Effects
- [cle.c:write]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
