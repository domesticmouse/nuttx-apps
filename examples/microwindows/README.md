# microwindows

## Overview
Microwindows example (`microwindows`). Enable the Microwindows example application

## Interface
- `[Kconfig:EXAMPLES_MICROWINDOWS]` - Build configuration option `EXAMPLES_MICROWINDOWS`
- `[Kconfig:EXAMPLES_MICROWINDOWS_PROGNAME]` - Build configuration option `EXAMPLES_MICROWINDOWS_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_MICROWINDOWS_PROGNAME)`
- `[mwdemo_main.c:main]` - Application entry point `main()`
- `[mwdemo.c:MwUserInit]` - Public function `MwUserInit()`
- `[mwdemo.c:RegisterAppClass]` - Public function `RegisterAppClass()`
- `[mwdemo.c:CreateAppWindow]` - Public function `CreateAppWindow()`
- `[mwdemo.c:ChildWndProc]` - Public function `ChildWndProc()`
- `[mwdemo.c:WndProc]` - Public function `WndProc()`

## Invariants
- `[Kconfig:depends on GRAPHICS_MICROWINDOWS]` - Requires kernel/app configuration `GRAPHICS_MICROWINDOWS`
- `[Kconfig:depends on MICROWINDOWS_MWIN]` - Requires kernel/app configuration `MICROWINDOWS_MWIN`

## Side Effects
- None

## Verification
- Run: `make test`
