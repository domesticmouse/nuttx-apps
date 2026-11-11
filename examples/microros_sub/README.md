# microros_sub

## Overview
micro-ROS int32 subscriber example (`microros_sub`). Minimal micro-ROS subscriber that creates a node, subscribes to the topic /nuttx_sub with std_msgs/Int32, and prints each received value.  Drives an rclc_executor spin loop and is used together with microros_pub (or any external publisher) to validate the NuttX-native transport in the receive direction.

## Interface
- `[Kconfig:EXAMPLES_MICROROS_SUB]` - Build configuration option `EXAMPLES_MICROROS_SUB`
- `[Kconfig:EXAMPLES_MICROROS_SUB_PROGNAME]` - Build configuration option `EXAMPLES_MICROROS_SUB_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MICROROS_SUB_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MICROROS_SUB_PROGNAME}`
- `[microros_sub_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SYSTEM_MICROROS]` - Requires kernel/app configuration `SYSTEM_MICROROS`

## Side Effects
- `[microros_sub_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
