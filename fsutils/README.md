# Filesystem Utilities (`fsutils`)

## Overview
Groups filesystem formatting libraries (`mkfatfs`, `mksmartfs`, `mkgpt`, `mkmbr`), MTD flash management utilities (`flash_eraseall`, `flashtool`), configuration file parsers (`inifile`, `ipcfg`), and password file management (`passwd`) for NuttX.

## Subdirectories & Boundaries
- `flash_eraseall`: [./flash_eraseall/README.md](./flash_eraseall/README.md) - Bulk erase helper (`flash_eraseall()`) for MTD flash devices.
- `flashtool`: [./flashtool/README.md](./flashtool/README.md) - CLI tool (`flashtool`) for inspecting, reading, writing, and erasing MTD flash sectors.
- `inifile`: [./inifile/README.md](./inifile/README.md) - Key-value INI configuration file reader library.
- `ipcfg`: [./ipcfg/README.md](./ipcfg/README.md) - Persistent text and binary IPv4/IPv6 network configuration file reader and writer.
- `mkfatfs`: [./mkfatfs/README.md](./mkfatfs/README.md) - FAT12/FAT16/FAT32 filesystem formatter (`mkfatfs()`) for NuttX block devices.
- `mkgpt`: [./mkgpt/README.md](./mkgpt/README.md) - GUID Partition Table (GPT) creation and verification CLI utility.
- `mkmbr`: [./mkmbr/README.md](./mkmbr/README.md) - Master Boot Record (MBR) partition table creation CLI utility.
- `mksmartfs`: [./mksmartfs/README.md](./mksmartfs/README.md) - SmartFS flash filesystem formatter (`mksmartfs()`) and format checker (`issmartfs()`).
- `passwd`: [./passwd/README.md](./passwd/README.md) - PBKDF2-HMAC-SHA256 `/etc/passwd` user management and authentication library.
