# nimble_blecent

## Overview
NimBLE central (`nimble_blecent`). Enable the nimble central example

## Interface
- `[Kconfig:EXAMPLES_NIMBLE_BLECENT]` - Build configuration option `EXAMPLES_NIMBLE_BLECENT`
- `[Kconfig:EXAMPLES_NIMBLE_BLECENT_PROGNAME]` - Build configuration option `EXAMPLES_NIMBLE_BLECENT_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_NIMBLE_BLECENT_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_NIMBLE_BLECENT_PROGNAME}`
- `[blecent.h:struct peer_dsc]` - Structure definition `peer_dsc`
- `[blecent.h:struct peer_chr]` - Structure definition `peer_chr`
- `[blecent.h:struct peer_svc]` - Structure definition `peer_svc`
- `[blecent.h:struct peer]` - Structure definition `peer`
- `[blecent.h:print_mbuf]` - Public function declaration `print_mbuf()`
- `[blecent.h:addr_str]` - Public function declaration `addr_str()`
- `[blecent.h:print_uuid]` - Public function declaration `print_uuid()`
- `[blecent.h:print_conn_desc]` - Public function declaration `print_conn_desc()`
- `[blecent.h:print_adv_fields]` - Public function declaration `print_adv_fields()`
- `[blecent.h:peer_disc_all]` - Public function declaration `peer_disc_all()`
- `[blecent.h:peer_delete]` - Public function declaration `peer_delete()`
- `[blecent.h:peer_add]` - Public function declaration `peer_add()`
- `[blecent.h:peer_init]` - Public function declaration `peer_init()`
- `[nimble_blecent_main.c:main]` - Application entry point `main()`
- `[misc.c:print_mbuf]` - Public function `print_mbuf()`
- `[misc.c:addr_str]` - Public function `addr_str()`
- `[misc.c:print_uuid]` - Public function `print_uuid()`
- `[misc.c:print_conn_desc]` - Public function `print_conn_desc()`
- `[misc.c:print_adv_fields]` - Public function `print_adv_fields()`
- `[peer.c:peer_svc_find_uuid]` - Public function `peer_svc_find_uuid()`
- `[peer.c:peer_chr_find_uuid]` - Public function `peer_chr_find_uuid()`
- `[peer.c:peer_dsc_find_uuid]` - Public function `peer_dsc_find_uuid()`
- `[peer.c:peer_disc_all]` - Public function `peer_disc_all()`
- `[peer.c:peer_delete]` - Public function `peer_delete()`
- `[peer.c:peer_add]` - Public function `peer_add()`
- `[peer.c:peer_init]` - Public function `peer_init()`

## Invariants
- `[nimble_blecent_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`
- `[nimble_blecent_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[nimble_blecent_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[misc.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
