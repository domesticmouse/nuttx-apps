# ble

## Overview
BLE sensor reading example (`ble`). Enable the BLE example

## Interface
- `[Kconfig:EXAMPLES_BLE]` - Build configuration option `EXAMPLES_BLE`
- `[Kconfig:EXAMPLES_BLE_PROGNAME]` - Build configuration option `EXAMPLES_BLE_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_BLE_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_BLE_PROGNAME}`
- `[sensors.h:get_temperature]` - Public function declaration `get_temperature()`
- `[sensors.h:get_pressure]` - Public function declaration `get_pressure()`
- `[sensors.h:get_gas_resistance]` - Public function declaration `get_gas_resistance()`
- `[sensors.h:get_humidity]` - Public function declaration `get_humidity()`
- `[sensors.h:monitor_sensors]` - Public function declaration `monitor_sensors()`
- `[sensors.h:init_sensors]` - Public function declaration `init_sensors()`
- `[sensors.h:close_sensors_fd]` - Public function declaration `close_sensors_fd()`
- `[ble.c:setup_ble]` - Public function `setup_ble()`
- `[ble_main.c:main]` - Application entry point `main()`
- `[dummy.c:get_temperature]` - Public function `get_temperature()`
- `[dummy.c:get_pressure]` - Public function `get_pressure()`
- `[dummy.c:get_gas_resistance]` - Public function `get_gas_resistance()`
- `[dummy.c:get_humidity]` - Public function `get_humidity()`
- `[dummy.c:monitor_sensors]` - Public function `monitor_sensors()`
- `[dummy.c:init_sensors]` - Public function `init_sensors()`
- `[dummy.c:close_sensors_fd]` - Public function `close_sensors_fd()`
- `[sensors.c:get_temperature]` - Public function `get_temperature()`
- `[sensors.c:get_pressure]` - Public function `get_pressure()`
- `[sensors.c:get_gas_resistance]` - Public function `get_gas_resistance()`
- `[sensors.c:get_humidity]` - Public function `get_humidity()`
- `[sensors.c:monitor_sensors]` - Public function `monitor_sensors()`
- `[sensors.c:init_sensors]` - Public function `init_sensors()`
- `[sensors.c:close_sensors_fd]` - Public function `close_sensors_fd()`

## Invariants
- `[Kconfig:depends on WIRELESS_BLUETOOTH]` - Requires kernel/app configuration `WIRELESS_BLUETOOTH`
- `[Kconfig:depends on SENSORS_BME680]` - Requires kernel/app configuration `SENSORS_BME680`

## Side Effects
- `[ble.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[ble.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[ble_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[ble_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[sensors.c:/dev/uorb/sensor_baro0]` - Opens or interacts with VFS/device path `/dev/uorb/sensor_baro0`
- `[sensors.c:/dev/uorb/sensor_gas0]` - Opens or interacts with VFS/device path `/dev/uorb/sensor_gas0`
- `[sensors.c:/dev/uorb/sensor_humi0]` - Opens or interacts with VFS/device path `/dev/uorb/sensor_humi0`
- `[sensors.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[sensors.c:open]` - Opens device nodes or files via `open()`
- `[sensors.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[sensors.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
