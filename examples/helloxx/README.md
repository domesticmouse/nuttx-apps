# helloxx

## Overview
"Hello, World!" C++ example (`helloxx`). Enable the "Hello, World!" C++ example

## Interface
- `[Kconfig:EXAMPLES_HELLOXX]` - Build configuration option `EXAMPLES_HELLOXX`
- `[Makefile:PROGNAME]` - Registers application/module target `helloxx`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `helloxx`
- `[helloxx_main.cxx:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on HAVE_CXX]` - Requires kernel/app configuration `HAVE_CXX`
- `[helloxx_main.cxx:CONFIG_DEBUG_FEATURES]` - Configuration guard on `CONFIG_DEBUG_FEATURES`
- `[helloxx_main.cxx:CONFIG_DEBUG_CXX]` - Configuration guard on `CONFIG_DEBUG_CXX`
- `[helloxx_main.cxx:CONFIG_HAVE_CXXINITIALIZE]` - Configuration guard on `CONFIG_HAVE_CXXINITIALIZE`

## Side Effects
- `[helloxx_main.cxx:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
