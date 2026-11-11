# mlx90614

## Overview
MLX90614 Test Example (`mlx90614`). Enable the MLX90614 example

## Interface
- `[Kconfig:EXAMPLES_MLX90614]` - Build configuration option `EXAMPLES_MLX90614`
- `[Kconfig:EXAMPLES_MLX90614_PROGNAME]` - Build configuration option `EXAMPLES_MLX90614_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MLX90614_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MLX90614_PROGNAME}`
- `[mlx90614_main.c:main]` - Application entry point `main()`

## Invariants
- `[mlx90614_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[mlx90614_main.c:/dev/therm0]` - Opens or interacts with VFS/device path `/dev/therm0`
- `[mlx90614_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[mlx90614_main.c:open]` - Opens device nodes or files via `open()`
- `[mlx90614_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[mlx90614_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
