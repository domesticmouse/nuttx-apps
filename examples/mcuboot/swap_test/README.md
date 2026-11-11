# swap_test

## Overview
MCUboot SWAP Test image example (`mcuboot/swap_test`). Example application to demonstrate the firmware image swap and the image rollback processes of MCUboot using the boot swap and test method.

## Interface
- `[Kconfig:EXAMPLES_MCUBOOT_SWAP_TEST]` - Build configuration option `EXAMPLES_MCUBOOT_SWAP_TEST`
- `[Makefile:PROGNAME]` - Registers application/module target `mcuboot_confirm mcuboot_set_img mcuboot_version`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `mcuboot_confirm`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `mcuboot_set_img`
- `[confirm_main.c:main]` - Application entry point `main()`
- `[set_img_main.c:main]` - Application entry point `main()`
- `[version_main.c:struct mcuboot_raw_version_v1_s]` - Structure definition `mcuboot_raw_version_v1_s`
- `[version_main.c:struct mcuboot_raw_header_v1_s]` - Structure definition `mcuboot_raw_header_v1_s`
- `[version_main.c:main]` - Application entry point `main()`

## Invariants
- None

## Side Effects
- `[confirm_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[set_img_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[set_img_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[version_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
