# cordic

## Overview
CORDIC example (`cordic`). Enable the CORDIC example

## Interface
- `[Kconfig:EXAMPLES_CORDIC]` - Build configuration option `EXAMPLES_CORDIC`
- `[Kconfig:EXAMPLES_CORDIC_DEVPATH]` - Build configuration option `EXAMPLES_CORDIC_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_CORDIC_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_CORDIC_PROGNAME}`
- `[cordic_main.c:main]` - Application entry point `main()`

## Invariants
- `[cordic_main.c:#error]` - Compile-time precondition: Not supported
- `[cordic_main.c:#error]` - Compile-time precondition: CONFIG_LIBC_FLOATINGPOINT must be enabled
- `[cordic_main.c:CONFIG_MATH_CORDIC_USE_Q31]` - Configuration guard on `CONFIG_MATH_CORDIC_USE_Q31`
- `[cordic_main.c:CONFIG_LIBC_FLOATINGPOINT]` - Configuration guard on `CONFIG_LIBC_FLOATINGPOINT`

## Side Effects
- `[cordic_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[cordic_main.c:open]` - Opens device nodes or files via `open()`
- `[cordic_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
