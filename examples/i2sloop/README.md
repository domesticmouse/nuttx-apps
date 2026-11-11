# i2sloop

## Overview
I2S loopback test (`i2sloop`). Enable the I2S loopback test

## Interface
- `[Kconfig:EXAMPLES_I2SLOOP]` - Build configuration option `EXAMPLES_I2SLOOP`
- `[Makefile:PROGNAME]` - Registers application/module target `i2sloop`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `i2sloop`
- `[i2sloop_main.c:main]` - Application entry point `main()`
- `[i2sloop_main.c:getopt]` - Command-line option parser supporting flags `"c:f:"`

## Invariants
- `[Kconfig:depends on I2S && AUDIO && DRIVERS_AUDIO && AUDIO_I2SCHAR && ENABLE_ALL_SIGNALS]` - Requires kernel/app configuration `I2S && AUDIO && DRIVERS_AUDIO && AUDIO_I2SCHAR && ENABLE_ALL_SIGNALS`
- `[i2sloop_main.c:DEBUGASSERT]` - Runtime state and non-null pointer assertions via `DEBUGASSERT()`

## Side Effects
- `[i2sloop_main.c:/dev/i2schar0]` - Opens or interacts with VFS/device path `/dev/i2schar0`
- `[i2sloop_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[i2sloop_main.c:open]` - Opens device nodes or files via `open()`
- `[i2sloop_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[i2sloop_main.c:write]` - Writes bytes to file or device descriptors via `write()`

## Verification
- Run: `make test`
