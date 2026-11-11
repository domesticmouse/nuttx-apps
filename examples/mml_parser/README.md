# mml_parser

## Overview
mml_parser example (`mml_parser`). Enable the mml_parser example

## Interface
- `[Kconfig:EXAMPLES_MMLPARSER]` - Build configuration option `EXAMPLES_MMLPARSER`
- `[Makefile:PROGNAME]` - Registers application/module target `mmlparser`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `mmlparser`
- `[mml_parser_main.c:print_parse_result]` - Public function `print_parse_result()`
- `[mml_parser_main.c:main]` - Application entry point `main()`

## Invariants
- `[mml_parser_main.c:#error]` - Compile-time precondition: This example needs to enable config of AUDIOUTILS_MMLPARSER_LIB,
- `[mml_parser_main.c:CONFIG_AUDIOUTILS_MMLPARSER_LIB]` - Configuration guard on `CONFIG_AUDIOUTILS_MMLPARSER_LIB`

## Side Effects
- `[mml_parser_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
