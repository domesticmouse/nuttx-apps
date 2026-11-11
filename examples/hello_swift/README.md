# hello_swift

## Overview
"Hello, Swift!" Swift embedded example (`hello_swift`). Enable the "Hello, Swift!" Swift embedded example

## Interface
- `[Kconfig:EXAMPLES_HELLO_SWIFT]` - Build configuration option `EXAMPLES_HELLO_SWIFT`
- `[Kconfig:EXAMPLES_HELLO_SWIFT_PROGNAME]` - Build configuration option `EXAMPLES_HELLO_SWIFT_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_HELLO_SWIFT_PROGNAME)`
- `[hello_swift_main.swift:swiftMain]` - Swift function `swiftMain()`
- `[hello_swift_main.swift:cMain]` - Swift function `cMain()`

## Invariants
- `[hello_swift_main.swift:@_cdecl("hello_swift_main")]` - Exports C-compatible symbol `hello_swift_main` for NuttX task startup

## Side Effects
- `[hello_swift_main.swift:print]` - Writes greeting string to standard output

## Verification
- Run: `make test`
