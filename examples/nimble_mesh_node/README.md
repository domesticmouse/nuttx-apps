# nimble_mesh_node

## Overview
NimBLE Mesh Generic OnOff node example (`nimble_mesh_node`). Provisionable NimBLE Mesh node with a Generic OnOff Server.

## Interface
- `[Kconfig:EXAMPLES_NIMBLE_MESH_NODE]` - Build configuration option `EXAMPLES_NIMBLE_MESH_NODE`
- `[Kconfig:EXAMPLES_NIMBLE_MESH_NODE_PROGNAME]` - Build configuration option `EXAMPLES_NIMBLE_MESH_NODE_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NIMBLE_MESH_NODE_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NIMBLE_MESH_NODE_PROGNAME}`
- `[nimble_mesh_node_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on NIMBLE_MESH]` - Requires kernel/app configuration `NIMBLE_MESH`
- `[nimble_mesh_node_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`

## Side Effects
- `[nimble_mesh_node_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[nimble_mesh_node_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
