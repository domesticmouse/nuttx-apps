# relays

## Overview
wget JSON Example (`relays`). Enable the wget JSON example

## Interface
- `[Kconfig:EXAMPLES_RELAYS]` - Build configuration option `EXAMPLES_RELAYS`
- `[Kconfig:EXAMPLES_RELAYS_NRELAYS]` - Build configuration option `EXAMPLES_RELAYS_NRELAYS`
- `[Makefile:PROGNAME]` - Registers application/module target `relays`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `relays`
- `[relays_main.c:main]` - Application entry point `main()`
- `[relays_main.c:getopt]` - Command-line option parser supporting flags `":n:"`

## Invariants
- `[Kconfig:depends on NETUTILS_JSON]` - Requires kernel/app configuration `NETUTILS_JSON`
- `[Kconfig:depends on ARCH_RELAYS]` - Requires kernel/app configuration `ARCH_RELAYS`
- `[relays_main.c:CONFIG_ARCH_RELAYS]` - Configuration guard on `CONFIG_ARCH_RELAYS`
- `[relays_main.c:CONFIG_EXAMPLES_RELAYS_NRELAYS]` - Configuration guard on `CONFIG_EXAMPLES_RELAYS_NRELAYS`

## Side Effects
- `[relays_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
