# pca9635

## Overview
PCA9635 PWM LED example (`pca9635`). Enable the PCA9635 example

## Interface
- `[Kconfig:EXAMPLES_PCA9635]` - Build configuration option `EXAMPLES_PCA9635`
- `[Kconfig:EXAMPLES_PCA9635_PROGNAME]` - Build configuration option `EXAMPLES_PCA9635_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_PCA9635_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_PCA9635_PROGNAME}`
- `[pca9635_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on PCA9635PW]` - Requires kernel/app configuration `PCA9635PW`

## Side Effects
- `[pca9635_main.c:/dev/leddrv0]` - Opens or interacts with VFS/device path `/dev/leddrv0`
- `[pca9635_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[pca9635_main.c:open]` - Opens device nodes or files via `open()`

## Verification
- Run: `make test`
