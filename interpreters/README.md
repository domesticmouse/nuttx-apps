# `interpreters`

## Overview
Groups Interpreters (`interpreters`) components and utilities for NuttX.

## Subdirectories & Boundaries
- `bas`: [./bas/README.md](./bas/README.md) - Provides Basic Interpreter support (`interpreters/bas`). This is a Basic interpreter written by Michael Haardt
- `berry`: [./berry/README.md](./berry/README.md) - Provides Berry scripting language (`interpreters/berry`). Enable the Berry embedded scripting language as an NSH built-in command. Berry provides a small ANSI C99 compiler, register-based
- `ficl`: [./ficl/README.md](./ficl/README.md) - Provides Ficl Forth interpreter (`interpreters/ficl`). Enable support for the Ficl interpreter interpreter. See README.txt file in the apps/interpreters/ficl directory. Use of this configuration assumes
- `lua`: [./lua/README.md](./lua/README.md) - Provides Lua interpreter support (`interpreters/lua`). Embed Lua language interpreter. Select the Lua version with the INTERPRETERS_LUA_VERSION config.
- `minibasic`: [./minibasic/README.md](./minibasic/README.md) - Provides Mini Basic Interpreter support (`interpreters/minibasic`). This is a Basic interpreter written by Malcolm McLean
- `python`: [./python/README.md](./python/README.md) - Provides CPython (`interpreters/python`). Enable the CPython port to NuttX. This is a port of the Python interpreter to NuttX. Initially, it is tweaked to work with the
- `quickjs`: [./quickjs/README.md](./quickjs/README.md) - Provides QuickJS JavaScript interpreter (`interpreters/quickjs`). It's depend on libatomic, Not all platform support it.
- `toywasm`: [./toywasm/README.md](./toywasm/README.md) - Implements Toywasm Webassembly Runtime (`interpreters/toywasm`) for the NuttX application subsystem.
- `wamr`: [./wamr/README.md](./wamr/README.md) - Provides Webassembly Micro Runtime (`interpreters/wamr`). Version WAMR-09-29-2020 and later (include main) supported.
