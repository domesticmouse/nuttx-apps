# wgetjson

## Overview
wget JSON Example (`wgetjson`). Enable the wget JSON example

## Interface
- `[Kconfig:EXAMPLES_WGETJSON]` - Build configuration option `EXAMPLES_WGETJSON`
- `[Kconfig:EXAMPLES_WGETJSON_MAXSIZE]` - Build configuration option `EXAMPLES_WGETJSON_MAXSIZE`
- `[Makefile:PROGNAME]` - Registers application/module target `wgetjson`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `wgetjson`
- `[wgetjson_main.c:main]` - Application entry point `main()`
- `[wgetjson_main.c:getopt]` - Command-line option parser supporting flags `":pPD"`
- **webserver**: [`./webserver/README.md`](./webserver/README.md) - Intermediate grouping directory for `wgetjson/webserver`, organizing submodules: wgetjson.

## Invariants
- `[Kconfig:depends on NETUTILS_CJSON]` - Requires kernel/app configuration `NETUTILS_CJSON`
- `[wgetjson_main.c:CONFIG_EXAMPLES_WGETJSON_MAXSIZE]` - Configuration guard on `CONFIG_EXAMPLES_WGETJSON_MAXSIZE`
- `[wgetjson_main.c:CONFIG_EXAMPLES_WGETJSON_URL]` - Configuration guard on `CONFIG_EXAMPLES_WGETJSON_URL`
- `[wgetjson_main.c:CONFIG_EXAMPLES_WGETPOST_URL]` - Configuration guard on `CONFIG_EXAMPLES_WGETPOST_URL`

## Side Effects
- `[wgetjson_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
