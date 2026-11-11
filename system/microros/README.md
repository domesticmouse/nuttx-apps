# `system/microros`

## Overview
Provides micro-ROS Integration (`system/microros`). Enable micro-ROS integration for NuttX RTOS. Provides a ROS 2 client library for embedded and real-time systems.

## Subdirectories & Boundaries
- `micro_ros_lib`: [./micro_ros_lib/README.md](./micro_ros_lib/README.md) - Architectural grouping for `system/microros/micro_ros_lib`, organizing `include_override`.
- `transport`: [./transport/README.md](./transport/README.md) - Implements `system/microros/transport` source and header components (`microros_transport.c`, `microros_transport.h`, `microros_transport_serial.c`, `microros_transport_udp.c`) in the NuttX application tree.
