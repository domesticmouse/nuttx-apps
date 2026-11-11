# `include/fsutils`

## Overview
Implements `include/fsutils`: Call a block driver with the MDIOC_BULKERASE ioctl command. This will cause the MTD driver to erase all of the flash.

## Interface
- [flash_eraseall.h:flash_eraseall]
- [inifile.h:INIHANDLE]
- [inifile.h:inifile_initialize]
- [inifile.h:inifile_uninitialize]
- [inifile.h:inifile_read_string]
- [inifile.h:inifile_read_integer]
- [inifile.h:inifile_free_string]
- [ipcfg.h:enum ipv4cfg_bootproto_e]
- [ipcfg.h:struct ipv4cfg_s]
- [ipcfg.h:enum ipv6cfg_bootproto_e]
- [ipcfg.h:struct ipv6cfg_s]
- [ipcfg.h:ipcfg_read]
- [ipcfg.h:ipcfg_write]
- [ipcfg.h:IPCFG_HAVE_STATIC]
- [ipcfg.h:IPCFG_USE_DHCP]
- [ipcfg.h:IPCFG_USE_AUTOCONF]
- [mkfatfs.h:struct fat_format_s]
- [mkfatfs.h:mkfatfs]

## Invariants
- [ipcfg.h:CONFIG_IPCFG_WRITABLE]: Conditional compilation gated by `CONFIG_IPCFG_WRITABLE`.
- [mksmartfs.h:CONFIG_SMARTFS_MULTI_ROOT_DIRS]: Conditional compilation gated by `CONFIG_SMARTFS_MULTI_ROOT_DIRS`.
- [passwd.h:CONFIG_FSUTILS_PASSWD_READONLY]: Conditional compilation gated by `CONFIG_FSUTILS_PASSWD_READONLY`.

## Side Effects
- None

## Verification
- Run: `make test`
