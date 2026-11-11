# chat

## Overview
AT modem chat utility (`chat`). Enable the AT chat utility.

## Interface
- `[Kconfig:EXAMPLES_CHAT]` - Build configuration option `EXAMPLES_CHAT`
- `[Kconfig:EXAMPLES_CHAT_TTY_DEVNODE]` - Build configuration option `EXAMPLES_CHAT_TTY_DEVNODE`
- `[Makefile:PROGNAME]` - Registers application/module target `chat`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `chat`
- `[chat_main.c:struct chat_app]` - Structure definition `chat_app`
- `[chat_main.c:main]` - Application entry point `main()`

## Invariants
- `[chat_main.c:DEBUGASSERT]` - Runtime state and non-null pointer assertions via `DEBUGASSERT()`
- `[chat_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[chat_main.c:open]` - Opens device nodes or files via `open()`
- `[chat_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[chat_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
