# scl3300test

## Overview
SCL3300 inclinometer test program (`scl3300test`). Enable the Murata SCL3300 test program. It checks WHOAMI and the self-test, prints the device info, measures the noise in every operation mode, cycles the power-down policy and resets the device, using the driver's uORB topics and ioctls.

## Interface
- `[Kconfig:EXAMPLES_SCL3300TEST]` - Build configuration option `EXAMPLES_SCL3300TEST`
- `[Kconfig:EXAMPLES_SCL3300TEST_PROGNAME]` - Build configuration option `EXAMPLES_SCL3300TEST_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SCL3300TEST_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_SCL3300TEST_PROGNAME}`
- `[scl3300test_main.c:main]` - Application entry point `main()`
- `[scl3300test_main.c:getopt]` - Command-line option parser supporting flags `"n:h"`

## Invariants
- `[Kconfig:depends on SENSORS_SCL3300]` - Requires kernel/app configuration `SENSORS_SCL3300`
- `[scl3300test_main.c:CONFIG_SENSORS_USE_B16]` - Configuration guard on `CONFIG_SENSORS_USE_B16`
- `[scl3300test_main.c:CONFIG_SENSORS_SCL3300_ACCEL]` - Configuration guard on `CONFIG_SENSORS_SCL3300_ACCEL`

## Side Effects
- `[scl3300test_main.c:/dev/uorb/sensor_%s%d]` - Opens or interacts with VFS/device path `/dev/uorb/sensor_%s%d`
- `[scl3300test_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[scl3300test_main.c:open]` - Opens device nodes or files via `open()`
- `[scl3300test_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[scl3300test_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
