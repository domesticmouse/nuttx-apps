# `games/brickmatch`

## Overview
Brick-matching puzzle game (`brickmatch`) supporting LCD framebuffers (`/dev/fb0`) or WS2812 LED matrices with console key, digital joystick, gesture sensor, GPIO button, or touchscreen input.

## Interface
- [bm_main.c:main]
- [bm_main.c:init_board]
- [bm_main.c:move_board]
- [bm_main.c:check_board]
- [bm_main.c:draw_board]
- [bm_inputs.h:input_state_s]
- [bm_input_console.h:dev_input_init]
- [bm_input_console.h:dev_read_input]
- [Kconfig:CONFIG_GAMES_BRICKMATCH]

## Invariants
- [bm_main.c:main]: When `CONFIG_GAMES_BRICKMATCH_USE_LCD_SCREEN` is enabled, requires `state.vinfo.yres > CONFIG_GAMES_BRICKMATCH_YOFFSET` and virtual plane bounds `>= abs_xoff + screen.xres` and `abs_yoff + screen.yres`.
- [bm_input_touch.h:dev_read_input]: Requires `TOUCH_POS_VALID` and swipe delta `>= CONFIG_GAMES_BRICKMATCH_TOUCH_THRESHOLD` before emitting a movement direction.

## Side Effects
- [bm_main.c:main]: Installs `SIGTERM` handler, opens `/dev/fb0` or `CONFIG_GAMES_BRICKMATCH_LED_MATRIX_PATH` (`O_RDWR`), issues `FBIOGET_VIDEOINFO`/`FBIOGET_PLANEINFO`/`FBIO_UPDATE` `ioctl` calls, `mmap`s framebuffer memory or writes RGB24 LED pixels, and mutates global `board` state.
- [bm_input_console.h:init_termios], [bm_input_joystick.h:dev_input_init], [bm_input_gpio.h:dev_input_init], and [bm_input_touch.h:dev_input_init]: Configure raw terminal attributes (`tcsetattr`) or open/read joystick, gesture, GPIO, and touchscreen input devices.

## Verification
- Run: `make test`
