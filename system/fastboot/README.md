# `system/fastboot`

## Overview
Provides fastbootd (`system/fastboot`). Fastboot daemon supporting multiple transports concurrently. Enable at least one transport (USB, TCP, Serial).

## Interface
- [Makefile:PROGNAME=fastbootd]
- [Kconfig:CONFIG_SYSTEM_FASTBOOTD]
- [Kconfig:CONFIG_SYSTEM_FASTBOOTD_PRIORITY]
- [Kconfig:CONFIG_SYSTEM_FASTBOOTD_STACKSIZE]
- [Kconfig:CONFIG_SYSTEM_FASTBOOTD_DOWNLOAD_MAX]
- [fastboot.c:struct fastboot_var_s]
- [fastboot.c:struct fastboot_sparse_header_s]
- [fastboot.c:struct fastboot_chunk_header_s]
- [fastboot.c:struct fastboot_mem_s]
- [fastboot.c:struct fastboot_file_s]
- [fastboot.c:struct fastboot_transport_ops_s]
- [fastboot.c:struct fastboot_async_s]
- [fastboot.c:struct fastboot_ctx_s]
- [fastboot.c:struct fastboot_cmd_s]
- [fastboot.c:u]
- [fastboot.c:upload_param]
- [fastboot.c:fastboot_handler]
- [fastboot.c:main]

## Invariants
- [Kconfig:CONFIG_SYSTEM_FASTBOOTD]: Build and feature compilation gated by `CONFIG_SYSTEM_FASTBOOTD`.
- [Kconfig:CONFIG_SYSTEM_FASTBOOTD_PRIORITY]: Build and feature compilation gated by `CONFIG_SYSTEM_FASTBOOTD_PRIORITY`.
- [Kconfig:depends on USBFASTBOOT || (NET_TCP && NET_TCPBACKLOG) || SERIAL]: Requires Kconfig dependency condition `USBFASTBOOT || (NET_TCP && NET_TCPBACKLOG) || SERIAL`.
- [Kconfig:depends on USBFASTBOOT]: Requires Kconfig dependency condition `USBFASTBOOT`.
- [Kconfig:depends on BOARDCTL]: Requires Kconfig dependency condition `BOARDCTL`.
- [fastboot.c:sem_wait]: Synchronizes concurrent access across threads or critical sections.

## Side Effects
- [fastboot.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [fastboot.c:read]: Performs VFS file or device descriptor I/O operations.
- [fastboot.c:socket]: Performs network socket creation, binding, or protocol I/O.
- [fastboot.c:malloc]: Allocates or releases dynamic heap memory.
- [fastboot.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [fastboot.c:syslog]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
