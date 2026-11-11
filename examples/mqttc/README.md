# mqttc

## Overview
Enable MQTT-C Example (`mqttc`). Enable a simple MQTT-C publisher example

## Interface
- `[Kconfig:EXAMPLES_MQTTC]` - Build configuration option `EXAMPLES_MQTTC`
- `[Kconfig:EXAMPLES_MQTTC_PROGNAME]` - Build configuration option `EXAMPLES_MQTTC_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MQTTC_PROGNAME)`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MQTTC_SUB_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_MQTTC_PROGNAME}`
- `[mqttc_pub.c:struct mqttc_cfg_s]` - Structure definition `mqttc_cfg_s`
- `[mqttc_pub.c:struct mqtt_conn_context_s]` - Structure definition `mqtt_conn_context_s`
- `[mqttc_pub.c:main]` - Application entry point `main()`
- `[mqttc_sub.c:struct mqttc_cfg_s]` - Structure definition `mqttc_cfg_s`
- `[mqttc_sub.c:struct mqtt_conn_context_s]` - Structure definition `mqtt_conn_context_s`
- `[mqttc_sub.c:struct mqttc_reconnect_s]` - Structure definition `mqttc_reconnect_s`
- `[mqttc_sub.c:publish_callback]` - Public function `publish_callback()`
- `[mqttc_sub.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NETUTILS_MQTTC]` - Requires kernel/app configuration `NETUTILS_MQTTC`
- `[Kconfig:depends on EXAMPLES_MQTTC_SUB]` - Requires kernel/app configuration `EXAMPLES_MQTTC_SUB`
- `[Kconfig:depends on NETUTILS_MQTTC_WITH_MBEDTLS]` - Requires kernel/app configuration `NETUTILS_MQTTC_WITH_MBEDTLS`
- `[mqttc_pub.c:CONFIG_EXAMPLES_MQTTC_ALLOW_UNVERIFIED_TLS]` - Configuration guard on `CONFIG_EXAMPLES_MQTTC_ALLOW_UNVERIFIED_TLS`
- `[mqttc_sub.c:CONFIG_EXAMPLES_MQTTC_ALLOW_UNVERIFIED_TLS]` - Configuration guard on `CONFIG_EXAMPLES_MQTTC_ALLOW_UNVERIFIED_TLS`

## Side Effects
- `[mqttc_pub.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[mqttc_pub.c:connect]` - Connects sockets to remote peers via `connect()`
- `[mqttc_pub.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[mqttc_pub.c:printf]` - Writes formatted output to standard output via `printf()`
- `[mqttc_sub.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[mqttc_sub.c:connect]` - Connects sockets to remote peers via `connect()`
- `[mqttc_sub.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[mqttc_sub.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
