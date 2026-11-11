# nxmbserver

## Overview
NxModbus Server Example (`nxmbserver`). Enable the NxModbus server example. This example demonstrates how to create a Modbus server (slave) that responds to client requests. Supports RTU, ASCII, and TCP transports with simulated register data.

## Interface
- `[Kconfig:EXAMPLES_NXMBSERVER]` - Build configuration option `EXAMPLES_NXMBSERVER`
- `[Kconfig:EXAMPLES_NXMBSERVER_PROGNAME]` - Build configuration option `EXAMPLES_NXMBSERVER_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NXMBSERVER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NXMBSERVER_PROGNAME}`
- `[nxmbserver_main.c:struct server_data_s]` - Structure definition `server_data_s`
- `[nxmbserver_main.c:struct server_config_s]` - Structure definition `server_config_s`
- `[nxmbserver_main.c:enum transport_type_e]` - Enumeration `transport_type_e`
- `[nxmbserver_main.c:main]` - Application entry point `main()`
- `[nxmbserver_main.c:getopt]` - Command-line option parser supporting flags `"t:d:b:p:a:P:u:h"`

## Invariants
- `[Kconfig:depends on NXMODBUS_SERVER]` - Requires kernel/app configuration `NXMODBUS_SERVER`

## Side Effects
- `[nxmbserver_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
