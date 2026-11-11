# igmp

## Overview
IGMP example (`igmp`). Enable the IGMP example

## Interface
- `[Kconfig:EXAMPLES_IGMP]` - Build configuration option `EXAMPLES_IGMP`
- `[Kconfig:EXAMPLES_IGMP_IPADDR]` - Build configuration option `EXAMPLES_IGMP_IPADDR`
- `[Makefile:PROGNAME]` - Registers application/module target `igmp`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `igmp`
- `[igmp.c:main]` - Application entry point `main()`

## Invariants
- `[igmp.c:#error]` - Compile-time precondition: Bad range for IGMP group address
- `[igmp.c:CONFIG_EXAMPLES_IGMP_GRPADDR]` - Configuration guard on `CONFIG_EXAMPLES_IGMP_GRPADDR`
- `[igmp.c:CONFIG_EXAMPLES_IGMP_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_IGMP_NOMAC`

## Side Effects
- `[igmp.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
