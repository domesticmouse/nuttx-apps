# optee_gp

## Overview
OP-TEE GP API client example (`optee_gp`). Enable the OP-TEE GP API client example which uses libteec

## Interface
- `[Kconfig:EXAMPLES_OPTEE_GP]` - Build configuration option `EXAMPLES_OPTEE_GP`
- `[Kconfig:EXAMPLES_OPTEE_GP_PROGNAME]` - Build configuration option `EXAMPLES_OPTEE_GP_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_OPTEE_GP_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_OPTEE_GP_PROGNAME}`
- `[optee_gp_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on LIBTEEC]` - Requires kernel/app configuration `LIBTEEC`

## Side Effects
- None

## Verification
- Run: `make test`
