# modbusmaster

## Overview
Modbus Master example (`modbusmaster`). Enable the Modbus Master example

## Interface
- `[Kconfig:EXAMPLES_MODBUSMASTER]` - Build configuration option `EXAMPLES_MODBUSMASTER`
- `[Kconfig:EXAMPLES_MODBUSMASTER_PROGNAME]` - Build configuration option `EXAMPLES_MODBUSMASTER_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MODBUSMASTER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MODBUSMASTER_PROGNAME}`
- `[mbmaster_main.c:struct mbmaster_statistics_s]` - Structure definition `mbmaster_statistics_s`
- `[mbmaster_main.c:struct mbmaster_run_s]` - Structure definition `mbmaster_run_s`
- `[mbmaster_main.c:enum mbmaster_threadcmd_e]` - Enumeration `mbmaster_threadcmd_e`
- `[mbmaster_main.c:eMBMasterRegHoldingCB]` - Public function `eMBMasterRegHoldingCB()`
- `[mbmaster_main.c:main]` - Application entry point `main()`

## Invariants
- `[mbmaster_main.c:CONFIG_EXAMPLES_MODBUSMASTER_PORT]` - Configuration guard on `CONFIG_EXAMPLES_MODBUSMASTER_PORT`
- `[mbmaster_main.c:CONFIG_EXAMPLES_MODBUSMASTER_BAUDRATE]` - Configuration guard on `CONFIG_EXAMPLES_MODBUSMASTER_BAUDRATE`
- `[mbmaster_main.c:CONFIG_EXAMPLES_MODBUSMASTER_PARITY]` - Configuration guard on `CONFIG_EXAMPLES_MODBUSMASTER_PARITY`
- `[mbmaster_main.c:CONFIG_EXAMPLES_MODBUSMASTER_SLAVEADDR]` - Configuration guard on `CONFIG_EXAMPLES_MODBUSMASTER_SLAVEADDR`

## Side Effects
- `[mbmaster_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[mbmaster_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
