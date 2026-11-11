# update_agent

## Overview
MCUboot update agent example (`mcuboot/update_agent`). Example application that implements an update agent that downloads an application firmware image from a given URL and saves it to the secondary slot as a pending update.

## Interface
- `[Kconfig:EXAMPLES_MCUBOOT_UPDATE_AGENT]` - Build configuration option `EXAMPLES_MCUBOOT_UPDATE_AGENT`
- `[Kconfig:EXAMPLES_MCUBOOT_UPDATE_AGENT_UPDATE_URL]` - Build configuration option `EXAMPLES_MCUBOOT_UPDATE_AGENT_UPDATE_URL`
- `[Makefile:PROGNAME]` - Registers application/module target `mcuboot_agent`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `mcuboot_agent`
- `[mcuboot_agent_main.c:struct download_context_s]` - Structure definition `download_context_s`
- `[mcuboot_agent_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NET_TCP]` - Requires kernel/app configuration `NET_TCP`
- `[Kconfig:depends on CODECS_HASH_MD5]` - Requires kernel/app configuration `CODECS_HASH_MD5`
- `[Kconfig:depends on EXAMPLES_MCUBOOT_UPDATE_AGENT_DL_VERIFY_MD5]` - Requires kernel/app configuration `EXAMPLES_MCUBOOT_UPDATE_AGENT_DL_VERIFY_MD5`
- `[mcuboot_agent_main.c:CONFIG_EXAMPLES_MCUBOOT_UPDATE_AGENT_DL_VERIFY_MD5]` - Configuration guard on `CONFIG_EXAMPLES_MCUBOOT_UPDATE_AGENT_DL_VERIFY_MD5`
- `[mcuboot_agent_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[mcuboot_agent_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[mcuboot_agent_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
