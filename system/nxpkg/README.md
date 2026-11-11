# `system/nxpkg`

## Overview
Provides 'nxpkg' lifecycle helper (`system/nxpkg`). Enable the thin package lifecycle helper proposed for the Dynamic ELF distribution work.

## Interface
- [Makefile:PROGNAME=$(CONFIG_SYSTEM_NXPKG_PROGNAME)]
- [Kconfig:CONFIG_SYSTEM_NXPKG]
- [Kconfig:CONFIG_SYSTEM_NXPKG_PROGNAME]
- [Kconfig:CONFIG_SYSTEM_NXPKG_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_NXPKG_STACKSIZE]
- [pkg.h:enum pkg_txn_state_e]
- [pkg.h:pkg_malloc]
- [pkg.h:pkg_zalloc]
- [pkg.h:pkg_realloc]
- [pkg.h:pkg_free]
- [pkg.h:pkg_manifest_type_str]
- [pkg.h:pkg_manifest_validate]
- [pkg.h:pkg_validate_path_component]
- [pkg.h:pkg_manifest_parse_type]
- [pkg.h:pkg_store_prepare_layout]
- [pkg.h:pkg_store_ensure_package_root]
- [pkg.h:pkg_store_ensure_version_dir]
- [pkg.h:pkg_store_format_index_path]

## Invariants
- [Kconfig:CONFIG_SYSTEM_NXPKG]: Build and feature compilation gated by `CONFIG_SYSTEM_NXPKG`.
- [Kconfig:CONFIG_SYSTEM_NXPKG_PROGNAME]: Build and feature compilation gated by `CONFIG_SYSTEM_NXPKG_PROGNAME`.
- [pkg_compat.c:CONFIG_ARCH_BOARD]: Conditional compilation gated by `CONFIG_ARCH_BOARD`.
- [pkg_repo.c:CONFIG_NETUTILS_WEBCLIENT]: Conditional compilation gated by `CONFIG_NETUTILS_WEBCLIENT`.
- [pkg_store.c:CONFIG_PSEUDOFS_FILE]: Conditional compilation gated by `CONFIG_PSEUDOFS_FILE`.

## Side Effects
- [pkg.h:malloc]: Allocates or releases dynamic heap memory.
- [pkg_hash.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [pkg_log.c:syslog]: Writes formatted diagnostic, logging, or console output.
- [pkg_main.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [pkg_metadata.c:fprintf]: Writes formatted diagnostic, logging, or console output.
- [pkg_repo.c:write]: Performs VFS file or device descriptor I/O operations.

## Verification
- Run: `make test`
