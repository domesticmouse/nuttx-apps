# fmsynth

## Overview
FM Synthesizer examples (`fmsynth`). Examples for fmsynth library.

## Interface
- `[Kconfig:EXAMPLES_FMSYNTH]` - Build configuration option `EXAMPLES_FMSYNTH`
- `[Kconfig:EXAMPLES_FMSYNTH_KEYBOARD_PROGNAME]` - Build configuration option `EXAMPLES_FMSYNTH_KEYBOARD_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_FMSYNTH_KEYBOARD_PROGNAME)`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_FMSYNTH_MMLPLAYER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_FMSYNTH_KEYBOARD_PROGNAME}`
- `[operator_algorithm.h:fmsynthutil_algorithm0]` - Public function declaration `fmsynthutil_algorithm0()`
- `[operator_algorithm.h:fmsynthutil_algorithm1]` - Public function declaration `fmsynthutil_algorithm1()`
- `[operator_algorithm.h:fmsynthutil_algorithm2]` - Public function declaration `fmsynthutil_algorithm2()`
- `[keyboard_main.c:struct app_options]` - Structure definition `app_options`
- `[keyboard_main.c:struct kbd_s]` - Structure definition `kbd_s`
- `[keyboard_main.c:struct key_convert_s]` - Structure definition `key_convert_s`
- `[keyboard_main.c:main]` - Application entry point `main()`
- `[keyboard_main.c:getopt]` - Command-line option parser supporting flags `"hv:m:"`
- `[mmlplayer_main.c:struct app_options]` - Structure definition `app_options`
- `[mmlplayer_main.c:struct mmlplayer_s]` - Structure definition `mmlplayer_s`
- `[mmlplayer_main.c:main]` - Application entry point `main()`
- `[mmlplayer_main.c:getopt]` - Command-line option parser supporting flags `"hv:m:"`
- `[operator_algorithm.c:fmsynthutil_algorithm0]` - Public function `fmsynthutil_algorithm0()`
- `[operator_algorithm.c:fmsynthutil_algorithm1]` - Public function `fmsynthutil_algorithm1()`
- `[operator_algorithm.c:fmsynthutil_algorithm2]` - Public function `fmsynthutil_algorithm2()`
- `[operator_algorithm.c:fmsynthutil_delete_ops]` - Public function `fmsynthutil_delete_ops()`

## Invariants
- None

## Side Effects
- `[keyboard_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[keyboard_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[mmlplayer_main.c:pthread_create]` - Spawns POSIX threads via `pthread_create()`
- `[mmlplayer_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
