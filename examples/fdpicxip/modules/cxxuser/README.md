# cxxuser

## Overview
NuttX `fdpicxip/modules/cxxuser` component: A C++ module using a C++ shared library. Two instances of this run at once in the demo.  Between them they show the three things that have to hold: - constructors ran, in both objects.  Neither magic can be right by accident: an unconstructed global is zero. - the library's constructors ran before t

## Interface
- `[Makefile:PROGNAME]` - Registers application/module target `cxxuser`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `cxxuser`
- `[cxxuser.cpp:class Instance]` - C++ class `Instance`
- `[cxxuser.cpp:main]` - Application entry point `main()`

## Invariants
- `[cxxuser.cpp:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[cxxuser.cpp:open]` - Opens device nodes or files via `open()`
- `[cxxuser.cpp:write]` - Writes bytes to file or device descriptors via `write()`
- `[cxxuser.cpp:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
