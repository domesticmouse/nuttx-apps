# `games/match4`

## Overview
Provides Match 4 Game (`games/match4`). Enable Match 4 game.

## Interface
- [Makefile:PROGNAME=$(CONFIG_GAMES_MATCH4_PROGNAME)]
- [Kconfig:CONFIG_GAMES_MATCH4]
- [Kconfig:CONFIG_GAMES_MATCH4_PROGNAME]
- [Kconfig:CONFIG_GAMES_MATCH4_PRIORITY]
- [Kconfig:CONFIG_GAMES_MATCH4_STACKSIZE]
- [match4_input_console.h:init_termios]
- [match4_input_console.h:deinit_termios]
- [match4_input_console.h:reset_termios]
- [match4_input_console.h:getch_]
- [match4_input_console.h:getch]
- [match4_input_console.h:dev_input_init]
- [match4_input_console.h:dev_input_deinit]
- [match4_input_console.h:dev_read_input]
- [match4_input_gpio.h:struct gpio_struct_fd_s]
- [match4_input_gpio.h:dev_input_init]
- [match4_input_gpio.h:dev_input_deinit]
- [match4_input_gpio.h:dev_read_input]
- [match4_inputs.h:struct input_state_s]

## Invariants
- [Kconfig:CONFIG_GAMES_MATCH4]: Build and feature compilation gated by `CONFIG_GAMES_MATCH4`.
- [Kconfig:CONFIG_GAMES_MATCH4_PROGNAME]: Build and feature compilation gated by `CONFIG_GAMES_MATCH4_PROGNAME`.
- [match4_inputs.h:CONFIG_GAMES_MATCH4_USE_CONSOLEKEY]: Conditional compilation gated by `CONFIG_GAMES_MATCH4_USE_CONSOLEKEY`.
- [match4_inputs.h:CONFIG_GAMES_MATCH4_USE_GPIO]: Conditional compilation gated by `CONFIG_GAMES_MATCH4_USE_GPIO`.
- [match4_main.c:CONFIG_GAMES_MATCH4_USE_CONSOLEKEY]: Conditional compilation gated by `CONFIG_GAMES_MATCH4_USE_CONSOLEKEY`.
- [match4_main.c:CONFIG_GAMES_MATCH4_USE_GPIO]: Conditional compilation gated by `CONFIG_GAMES_MATCH4_USE_GPIO`.

## Side Effects
- [match4_input_gpio.h:ioctl]: Issues device/driver control requests via `ioctl()`.
- [match4_input_gpio.h:open]: Performs VFS file or device descriptor I/O operations.
- [match4_input_gpio.h:fprintf]: Writes formatted diagnostic, logging, or console output.
- [match4_main.c:write]: Performs VFS file or device descriptor I/O operations.
- [match4_main.c:printf]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
