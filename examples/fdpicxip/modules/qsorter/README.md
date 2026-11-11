# qsorter

## Overview
NuttX `fdpicxip/modules/qsorter` component: Demonstrates the two things worth knowing about NuttX FDPIC modules. 1. qsort() runs in the firmware and calls back into compare(), which lives here.  That works because the firmware reserves the FDPIC register, so this module's data base survives the call in, and because libc resolves the callback 

## Interface
- `[Makefile:PROGNAME]` - Registers application/module target `qsorter`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `qsorter`
- `[qsorter.c:main]` - Application entry point `main()`

## Invariants
- `[qsorter.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[qsorter.c:syslog]` - Writes diagnostic log entries via `syslog()`

## Verification
- Run: `make test`
