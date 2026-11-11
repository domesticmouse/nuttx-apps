# `interpreters/python`

## Overview
Provides CPython (`interpreters/python`). Enable the CPython port to NuttX. This is a port of the Python interpreter to NuttX. Initially, it is tweaked to work with the

## Interface
- [Makefile:PROGNAME=$(CONFIG_INTERPRETERS_CPYTHON_PROGNAME)]
- [Kconfig:CONFIG_INTERPRETERS_CPYTHON]
- [Kconfig:CONFIG_INTERPRETERS_CPYTHON_VERSION]
- [Kconfig:CONFIG_INTERPRETERS_CPYTHON_STACKSIZE]
- [Kconfig:CONFIG_INTERPRETERS_CPYTHON_PRIORITY]
- [python_wrapper.c:main]
- [repack_wheel_add_pyc.py:wheel_record_hash]
- [repack_wheel_add_pyc.py:wheel_has_py_sources]
- [repack_wheel_add_pyc.py:wheel_has_legacy_bytecode]
- [repack_wheel_add_pyc.py:strip_py_sources]
- [repack_wheel_add_pyc.py:rebuild_record]
- [repack_wheel_add_pyc.py:repack]
- [repack_wheel_add_pyc.py:main]
- [repack_wheel_add_pyc.py:__main__]

## Invariants
- [Kconfig:CONFIG_INTERPRETERS_CPYTHON]: Build and feature compilation gated by `CONFIG_INTERPRETERS_CPYTHON`.
- [Kconfig:CONFIG_INTERPRETERS_CPYTHON_VERSION]: Build and feature compilation gated by `CONFIG_INTERPRETERS_CPYTHON_VERSION`.
- [Kconfig:depends on LIB_ZLIB]: Requires Kconfig dependency condition `LIB_ZLIB`.
- [Kconfig:depends on !LIBC_DLFCN || LIB_LIBFFI]: Requires Kconfig dependency condition `!LIBC_DLFCN || LIB_LIBFFI`.
- [Kconfig:depends on EXPERIMENTAL]: Requires Kconfig dependency condition `EXPERIMENTAL`.
- [python_wrapper.c:CONFIG_SYSTEM_READLINE]: Conditional compilation gated by `CONFIG_SYSTEM_READLINE`.

## Side Effects
- [python_wrapper.c:fopen]: Performs VFS file or device descriptor I/O operations.
- [python_wrapper.c:printf]: Writes formatted diagnostic, logging, or console output.
- [repack_wheel_add_pyc.py:open]: Reads/writes host filesystem paths or invokes subprocesses.

## Verification
- Run: `make test`
