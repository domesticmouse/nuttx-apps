# xrcedds

## Overview
XRCEDDS publisher demo (`xrcedds`). Build the PublishHelloWorldClient command.  It connects to a Micro XRCE-DDS Agent through the built-in UDP transport and publishes HelloWorld samples.

## Interface
- `[Kconfig:EXAMPLES_XRCEDDS_PUB]` - Build configuration option `EXAMPLES_XRCEDDS_PUB`
- `[Kconfig:EXAMPLES_XRCEDDS_PUB_PROGNAME]` - Build configuration option `EXAMPLES_XRCEDDS_PUB_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_XRCEDDS_PUB_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_XRCEDDS_PUB_PROGNAME}`
- `[hello_world.h:struct hello_world_s]` - Structure definition `hello_world_s`
- `[hello_world.h:hello_world_serialize_topic]` - Public function declaration `hello_world_serialize_topic()`
- `[hello_world.h:hello_world_deserialize_topic]` - Public function declaration `hello_world_deserialize_topic()`
- `[hello_world.h:hello_world_topic_size]` - Public function declaration `hello_world_topic_size()`
- `[xrcedds_pub_main.c:main]` - Application entry point `main()`
- `[hello_world.c:hello_world_serialize_topic]` - Public function `hello_world_serialize_topic()`
- `[hello_world.c:hello_world_deserialize_topic]` - Public function `hello_world_deserialize_topic()`
- `[hello_world.c:hello_world_topic_size]` - Public function `hello_world_topic_size()`

## Invariants
- `[Kconfig:depends on SYSTEM_XRCEDDS && NET_UDP && NET_IPv4]` - Requires kernel/app configuration `SYSTEM_XRCEDDS && NET_UDP && NET_IPv4`
- `[xrcedds_pub_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[xrcedds_pub_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
