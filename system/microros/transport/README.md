# `system/microros/transport`

## Overview
Implements `system/microros/transport` source and header components (`microros_transport.c`, `microros_transport.h`, `microros_transport_serial.c`, `microros_transport_udp.c`) in the NuttX application tree.

## Interface
- [microros_transport.h:microros_udp_open]
- [microros_transport.h:microros_udp_close]
- [microros_transport.h:microros_udp_write]
- [microros_transport.h:microros_udp_read]
- [microros_transport.h:microros_serial_open]
- [microros_transport.h:microros_serial_close]
- [microros_transport.h:microros_serial_write]
- [microros_transport.h:microros_serial_read]
- [microros_transport.c:microros_transport_init]
- [microros_transport_serial.c:microros_serial_open]
- [microros_transport_serial.c:microros_serial_close]
- [microros_transport_serial.c:microros_serial_write]
- [microros_transport_serial.c:microros_serial_read]
- [microros_transport_udp.c:microros_udp_open]
- [microros_transport_udp.c:microros_udp_close]
- [microros_transport_udp.c:microros_udp_write]
- [microros_transport_udp.c:microros_udp_read]

## Invariants
- [microros_transport.c:CONFIG_MICROROS_TRANSPORT_UDP]: Conditional compilation gated by `CONFIG_MICROROS_TRANSPORT_UDP`.

## Side Effects
- [microros_transport_serial.c:open]: Performs VFS file or device descriptor I/O operations.
- [microros_transport_udp.c:close]: Performs VFS file or device descriptor I/O operations.
- [microros_transport_udp.c:socket]: Performs network socket creation, binding, or protocol I/O.

## Verification
- Run: `make test`
