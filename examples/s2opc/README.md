# s2opc

## Overview
S2OPC OPC UA server example (`s2opc`). Build a small S2OPC server with an anonymous SecurityPolicy None endpoint and an address space generated as C source.

## Interface
- `[Kconfig:EXAMPLES_S2OPC]` - Build configuration option `EXAMPLES_S2OPC`
- `[Kconfig:EXAMPLES_S2OPC_PROGNAME]` - Build configuration option `EXAMPLES_S2OPC_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_S2OPC_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `MODULE`
- `[s2opc_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NETUTILS_S2OPC]` - Requires kernel/app configuration `NETUTILS_S2OPC`
- `[s2opc_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[s2opc_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
