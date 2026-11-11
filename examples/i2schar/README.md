# i2schar

## Overview
I2S character driver test (`i2schar`). Enable the I2S character driver test

## Interface
- `[Kconfig:EXAMPLES_I2SCHAR]` - Build configuration option `EXAMPLES_I2SCHAR`
- `[Kconfig:EXAMPLES_I2SCHAR_DEVPATH]` - Build configuration option `EXAMPLES_I2SCHAR_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `i2schar`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `i2schar`
- `[i2schar.h:struct i2schar_state_s]` - Structure definition `i2schar_state_s`
- `[i2schar.h:i2schar_devinit]` - Public function declaration `i2schar_devinit()`
- `[i2schar.h:i2schar_transmitter]` - Public function declaration `i2schar_transmitter()`
- `[i2schar.h:i2schar_receiver]` - Public function declaration `i2schar_receiver()`
- `[i2schar_main.c:main]` - Application entry point `main()`
- `[i2schar_receiver.c:i2schar_receiver]` - Public function `i2schar_receiver()`
- `[i2schar_transmitter.c:i2schar_transmitter]` - Public function `i2schar_transmitter()`

## Invariants
- `[Kconfig:depends on I2S && AUDIO && DRIVERS_AUDIO && AUDIO_I2SCHAR]` - Requires kernel/app configuration `I2S && AUDIO && DRIVERS_AUDIO && AUDIO_I2SCHAR`
- `[Kconfig:depends on BUILD_FLAT]` - Requires kernel/app configuration `BUILD_FLAT`
- `[i2schar.h:#error]` - Compile-time precondition: I2S character device support is not enabled (CONFIG_AUDIO_I2SCHAR)
- `[i2schar.h:CONFIG_AUDIO_I2SCHAR]` - Configuration guard on `CONFIG_AUDIO_I2SCHAR`
- `[i2schar.h:CONFIG_EXAMPLES_I2SCHAR_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_I2SCHAR_DEVPATH`
- `[i2schar.h:CONFIG_EXAMPLES_I2SCHAR_TX]` - Configuration guard on `CONFIG_EXAMPLES_I2SCHAR_TX`
- `[i2schar.h:CONFIG_EXAMPLES_I2SCHAR_TXBUFFERS]` - Configuration guard on `CONFIG_EXAMPLES_I2SCHAR_TXBUFFERS`
- `[i2schar_main.c:CONFIG_EXAMPLES_I2SCHAR_TX]` - Configuration guard on `CONFIG_EXAMPLES_I2SCHAR_TX`
- `[i2schar_main.c:CONFIG_EXAMPLES_I2SCHAR_RX]` - Configuration guard on `CONFIG_EXAMPLES_I2SCHAR_RX`
- `[i2schar_main.c:CONFIG_EXAMPLES_I2SCHAR_DEVINIT]` - Configuration guard on `CONFIG_EXAMPLES_I2SCHAR_DEVINIT`
- `[i2schar_receiver.c:CONFIG_EXAMPLES_I2SCHAR_RX]` - Configuration guard on `CONFIG_EXAMPLES_I2SCHAR_RX`
- `[i2schar_transmitter.c:CONFIG_EXAMPLES_I2SCHAR_TX]` - Configuration guard on `CONFIG_EXAMPLES_I2SCHAR_TX`

## Side Effects
- `[i2schar.h:/dev/is2char0]` - Opens or interacts with VFS/device path `/dev/is2char0`
- `[i2schar_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[i2schar_main.c:open]` - Opens device nodes or files via `open()`
- `[i2schar_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[i2schar_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[i2schar_receiver.c:open]` - Opens device nodes or files via `open()`
- `[i2schar_receiver.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[i2schar_receiver.c:printf]` - Writes formatted output to standard output via `printf()`
- `[i2schar_transmitter.c:open]` - Opens device nodes or files via `open()`
- `[i2schar_transmitter.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[i2schar_transmitter.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
