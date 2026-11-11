# funcdesc

## Overview
NuttX `fdpicxip/modules/funcdesc` component: Exercises R_ARM_FUNCDESC -- the relocation that asks the loader to manufacture a function descriptor and hand back its address. It is emitted for an *address-taken imported* function, which is a different thing from a called one.  A call gets a PLT entry and an R_ARM_FUNCDESC_VALUE relocation on a d

## Interface
- `[Makefile:PROGNAME]` - Registers application/module target `funcdesc`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `funcdesc`
- `[funcdesc.c:main]` - Application entry point `main()`

## Invariants
- `[funcdesc.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[funcdesc.c:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
