# IP Configuration File Utility (`fsutils/ipcfg`)

## Overview
Provides persistent IPv4 and IPv6 network interface configuration storage and retrieval (`CONFIG_FSUTILS_IPCFG`), supporting both human-readable text key-value files and compact binary structures on VFS directories or character devices.

## Interface
- `[ipcfg.c:ipcfg_read]` / `[ipcfg.c:ipcfg_write]`: Public entry points for reading and writing IPv4/IPv6 network device configuration (`struct ipv4_cfg_s` / `struct ipv6_cfg_s`).
- `[ipcfg.h:ipcfg_header_s]`, `[ipcfg.h:IPCFG_VERSION]`, `[ipcfg.h:MAX_LINESIZE]`, `[ipcfg.h:MAX_IPv4PROTO]`, `[ipcfg.h:MAX_IPv6PROTO]`: Binary header layout and parser constants.
- `[ipcfg_binary.c:ipcfg_read_binary_ipv4]` / `[ipcfg_binary.c:ipcfg_read_binary_ipv6]` / `[ipcfg_binary.c:ipcfg_write_binary_ipv4]` / `[ipcfg_binary.c:ipcfg_write_binary_ipv6]`: Binary format backend helpers.
- `[ipcfg_text.c:ipcfg_read_text_ipv4]` / `[ipcfg_text.c:ipcfg_read_text_ipv6]` / `[ipcfg_text.c:ipcfg_write_text_ipv4]` / `[ipcfg_text.c:ipcfg_write_text_ipv6]`: Text format backend helpers.
- `[Kconfig:FSUTILS_IPCFG]`, `[Kconfig:IPCFG_WRITABLE]`, `[Kconfig:IPCFG_BINARY]`, `[Kconfig:IPCFG_PATH]`, `[Kconfig:IPCFG_CHARDEV]`, `[Kconfig:IPCFG_OFFSET]`: Build and storage configuration symbols.

## Invariants
- `[ipcfg.c:ipcfg_read]` and `[ipcfg.c:ipcfg_write]`: Require `netdev != NULL`, `ipcfg != NULL`, and address family `af` equal to `AF_INET` (when `CONFIG_NET_IPv4`) or `AF_INET6` (when `CONFIG_NET_IPv6`), returning `-EAFNOSUPPORT` otherwise.
- `[ipcfg_binary.c:ipcfg_find_binary]`: Binary record header version must equal `IPCFG_VERSION` (`1`) and type must be `AF_INET` or `AF_INET6`.
- `[ipcfg_text.c:ipcfg_write_ipv4]` and `[ipcfg_text.c:ipcfg_write_ipv6]`: Protocol enum values must not exceed `MAX_IPv4PROTO` / `MAX_IPv6PROTO`.
- `[Kconfig:IPCFG_CHARDEV]` and `[Kconfig:IPCFG_OFFSET]`: `IPCFG_CHARDEV` depends on `IPCFG_BINARY`, and `IPCFG_OFFSET` depends on `IPCFG_CHARDEV`.

## Side Effects
- `[ipcfg.c:ipcfg_allocpath]`: Dynamically allocates and frees path strings via `asprintf`/`strdup` and `free`.
- `[ipcfg_binary.c:ipcfg_open]`, `[ipcfg_binary.c:ipcfg_write_binary_ipv4]`, and `[ipcfg_text.c:ipcfg_write_text_ipv4]`: Open, seek (to `CONFIG_IPCFG_OFFSET` when configured), read, truncate, and rewrite binary or text configuration records under `CONFIG_IPCFG_PATH`, preserving existing dual-stack (IPv4/IPv6) records on update.

## Verification
- Run: `make test`
