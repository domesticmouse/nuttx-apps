# `interpreters/lua`

## Overview
Provides Lua interpreter support (`interpreters/lua`). Embed Lua language interpreter. Select the Lua version with the INTERPRETERS_LUA_VERSION config.

## Interface
- [Makefile:PROGNAME=lua]
- [Kconfig:CONFIG_INTERPRETERS_LUA]
- [Kconfig:CONFIG_INTERPRETERS_LUA_VERSION]
- [Kconfig:CONFIG_INTERPRETERS_LUA_CORELIBS]
- [Kconfig:CONFIG_INTERPRETERS_LUA_PATH]
- [nuttx_linit.c:luaL_openlibs]

## Invariants
- [Kconfig:CONFIG_INTERPRETERS_LUA]: Build and feature compilation gated by `CONFIG_INTERPRETERS_LUA`.
- [Kconfig:CONFIG_INTERPRETERS_LUA_VERSION]: Build and feature compilation gated by `CONFIG_INTERPRETERS_LUA_VERSION`.
- [nuttx_linit.c:CONFIG_INTERPRETERS_LUA_CORELIBS]: Conditional compilation gated by `CONFIG_INTERPRETERS_LUA_CORELIBS`.

## Side Effects
- None

## Verification
- Run: `make test`
