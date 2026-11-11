# SQLite Database Integration (`database/sqlite`)

## Overview
Provides the build wrapper and static platform configuration header (`sqlite_cfg.h`) for integrating the SQLite relational database library (`CONFIG_LIB_SQLITE`) and CLI shell utility (`CONFIG_UTILS_SQLITE`) into NuttX.

## Interface
- `[Kconfig:CONFIG_LIB_SQLITE]` / `[Kconfig:CONFIG_LIB_SQLITE_VERSION]`: Enables and configures the SQLite library build.
- `[Kconfig:CONFIG_UTILS_SQLITE]` / `[Kconfig:CONFIG_UTILS_SQLITE_STACKSIZE]`: Enables the `sqlite3` interactive CLI utility.
- `[Makefile:_HAVE_SQLITE_CONFIG_H]`, `[Makefile:NDEBUG]`: Compiler flags selecting the NuttX `sqlite_cfg.h` header.
- `[sqlite_cfg.h:PACKAGE_VERSION]`, `[sqlite_cfg.h:HAVE_FDATASYNC]`, `[sqlite_cfg.h:HAVE_PREAD]`, `[sqlite_cfg.h:HAVE_PWRITE]`, `[sqlite_cfg.h:HAVE_MALLOC_USABLE_SIZE]`, `[sqlite_cfg.h:HAVE_USLEEP]`, `[sqlite_cfg.h:HAVE_UTIME]`: Feature capability macros defining NuttX libc/POSIX support for SQLite.

## Invariants
- `[Kconfig:CONFIG_LIB_SQLITE]`: Depends on `CONFIG_FS_LOCK_BUCKET_SIZE > 0`.
- `[Kconfig:CONFIG_UTILS_SQLITE_STACKSIZE]`: Depends on `UTILS_SQLITE`.

## Side Effects
- `[Makefile:sqlite.zip]` and `[Makefile:context]`: Download the SQLite source archive from GitHub via `curl` (if `sqlite/.git` is absent) and invoke `sqlite/configure` and `make sqlite3.c` to generate the SQLite amalgamation at build time.
- `[CMakeLists.txt:sqlite_fetch]`: Fetches the SQLite archive via `FetchContent` and generates `sqlite3.c`, `sqlite3.h`, and `shell.c`.

## Verification
- Run: `make test`
