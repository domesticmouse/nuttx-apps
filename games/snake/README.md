# `games/snake`

## Overview
Classic Snake game (`snake`) rendered onto a WS2812 RGB LED matrix with console keyboard or GPIO directional button input.

## Interface
- [snake_main.c:main]
- [snake_inputs.h:input_state_s]
- [snake_input_console.h:dev_input_init]
- [snake_input_console.h:dev_read_input]
- [snake_input_gpio.h:dev_input_init]
- [snake_input_gpio.h:dev_read_input]
- [Kconfig:CONFIG_GAMES_SNAKE]

## Invariants
- [snake_main.c:main]: Disallows 180-degree opposite direction reversals (`DIR_LEFT` vs `DIR_RIGHT`, `DIR_UP` vs `DIR_DOWN`) by retaining `last_dir`.
- [snake_main.c:move_snake] and [snake_main.c:check_collisions]: Wrap snake head coordinates modulo `BOARDX_SIZE`/`BOARDY_SIZE` and set `game_over = true` when head `snake.tail[0]` collides with any tail segment.

## Side Effects
- [snake_main.c:main] and [snake_main.c:draw_board]: Seed PRNG via `srand(time(NULL))`, open `CONFIG_GAMES_SNAKE_LED_MATRIX_PATH` (`O_RDWR`), write gamma-corrected RGB24 frame bytes, and print score updates to `stdout`.
- [snake_input_console.h:dev_input_init] and [snake_input_gpio.h:dev_input_init]: Modify `termios` (`~ICANON`, `~ECHO`) and `O_NONBLOCK` flags on `STDIN_FILENO` or open GPIO key devices and issue `GPIOC_READ` `ioctl` calls.

## Verification
- Run: `make test`
