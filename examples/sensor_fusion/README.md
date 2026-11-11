# sensor_fusion

## Overview
Sensor Fusion Example (`sensor_fusion`). Sensor fusion example that combines gyro and accelerometer data using the Madgwick algorithm to provide yaw, pitch and roll angles.

## Interface
- `[Kconfig:EXAMPLES_SENSOR_FUSION]` - Build configuration option `EXAMPLES_SENSOR_FUSION`
- `[Kconfig:EXAMPLES_SENSOR_FUSION_SAMPLES]` - Build configuration option `EXAMPLES_SENSOR_FUSION_SAMPLES`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SENSOR_FUSION_PROGNAME)`
- `[sensor_fusion_main.c:struct mpu6050_imu_msg]` - Structure definition `mpu6050_imu_msg`
- `[sensor_fusion_main.c:main]` - Application entry point `main()`
- `[sensor_fusion_main.c:read_mpu6050]` - Public function `read_mpu6050()`

## Invariants
- None

## Side Effects
- `[sensor_fusion_main.c:/dev/imu0]` - Opens or interacts with VFS/device path `/dev/imu0`
- `[sensor_fusion_main.c:open]` - Opens device nodes or files via `open()`
- `[sensor_fusion_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[sensor_fusion_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
