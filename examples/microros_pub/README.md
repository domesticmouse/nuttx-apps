# microros_pub

## Overview
micro-ROS int32 publisher example (`microros_pub`). Minimal micro-ROS publisher that creates a node and publishes an std_msgs/Int32 every second on the topic /nuttx_pub.  Used to validate the NuttX-native transport layer end-to-end with a micro-ROS agent.

## Interface
- `[Kconfig:EXAMPLES_MICROROS_PUB]` - Build configuration option `EXAMPLES_MICROROS_PUB`
- `[Kconfig:EXAMPLES_MICROROS_PUB_PROGNAME]` - Build configuration option `EXAMPLES_MICROROS_PUB_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MICROROS_PUB_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MICROROS_PUB_PROGNAME}`
- `[microros_pub_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on SYSTEM_MICROROS]` - Requires kernel/app configuration `SYSTEM_MICROROS`

## Side Effects
- `[microros_pub_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
