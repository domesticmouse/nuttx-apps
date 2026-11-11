# etl

## Overview
Embedded Template Library (ETL) C++ example (`etl`). Enable the ETL C++ example which showcases the etl::vector container and C++11 iterator

## Interface
- `[Kconfig:EXAMPLES_ETL]` - Build configuration option `EXAMPLES_ETL`
- `[Makefile:PROGNAME]` - Registers application/module target `etl`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `etl`
- `[etl_main.cxx:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on HAVE_CXX && ETL]` - Requires kernel/app configuration `HAVE_CXX && ETL`
- `[etl_main.cxx:CONFIG_DEBUG_FEATURES]` - Configuration guard on `CONFIG_DEBUG_FEATURES`
- `[etl_main.cxx:CONFIG_DEBUG_CXX]` - Configuration guard on `CONFIG_DEBUG_CXX`
- `[etl_main.cxx:CONFIG_HAVE_CXXINITIALIZE]` - Configuration guard on `CONFIG_HAVE_CXXINITIALIZE`

## Side Effects
- `[etl_main.cxx:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
