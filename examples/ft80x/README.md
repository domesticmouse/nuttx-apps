# ft80x

## Overview
FT80x example (`ft80x`). Enable the FT80X example

## Interface
- `[ft80x.h:ft80x_err]` - Error logging macro mapped to `_none`, `fprintf(stderr, ...)`, or `printf` depending on `GRAPHICS_FT80X_DEBUG_ERROR` and `CONFIG_CPP_HAVE_VARARGS`
- `[ft80x.h:ft80x_warn]` - Warning logging macro mapped to `_none`, `fprintf(stderr, ...)`, or `printf` depending on `GRAPHICS_FT80X_DEBUG_WARN` and `CONFIG_CPP_HAVE_VARARGS`
- `[ft80x.h:ft80x_info]` - Info logging macro mapped to `_none` or `printf` depending on `GRAPHICS_FT80X_DEBUG_INFO` and `CONFIG_CPP_HAVE_VARARGS`
- `[ft80x.h:ft80x_example_t]` - Function pointer typedef `int (*ft80x_example_t)(int fd, FAR struct ft80x_dlbuffer_s *buffer)` for display example entry points
- `[ft80x.h:struct ft80x_bitmaphdr_s]` - Structure defining bitmap properties (`format`, `width`, `height`, `stride`, `offset`, `data`)
- `[ft80x_bitmaps.c:g_lenaface_bmhdr]` - Public `const struct ft80x_bitmaphdr_s` for the 40x40 RGB565 Lena face bitmap (guarded by `!CONFIG_EXAMPLES_FT80X_EXCLUDE_BITMAPS`)
- `[ft80x_main.c:main]` - Application entry point that opens `CONFIG_EXAMPLES_FT80X_DEVPATH`, allocates `struct ft80x_dlbuffer_s`, and runs primitive (`g_primitives`) and co-processor (`g_coproc`) example suites
- `[ft80x_primitives.c:ft80x_prim_bitmaps]` - Demonstrates the `FT80X_PRIM_BITMAPS` GPU primitive using `g_lenaface_bmhdr`
- `[ft80x_primitives.c:ft80x_prim_points]` - Demonstrates the `FT80X_PRIM_POINTS` GPU primitive with varying point sizes and colors
- `[ft80x_primitives.c:ft80x_prim_lines]` - Demonstrates the `FT80X_PRIM_LINES` GPU primitive with varying line widths and colors
- `[ft80x_primitives.c:ft80x_prim_linestrip]` - Demonstrates the `FT80X_PRIM_LINE_STRIP` GPU primitive
- `[ft80x_primitives.c:ft80x_prim_edgestrip_r]` - Demonstrates the `FT80X_PRIM_EDGE_STRIP_R` GPU primitive
- `[ft80x_primitives.c:ft80x_prim_rectangles]` - Demonstrates the `FT80X_PRIM_RECTS` GPU primitive with varying corner curvatures (`FT80X_LINE_WIDTH`)
- `[ft80x_primitives.c:ft80x_prim_scissor]` - Demonstrates `FT80X_SCISSOR_XY` and `FT80X_SCISSOR_SIZE` GPU commands
- `[ft80x_primitives.c:ft80x_prim_stencil]` - Demonstrates `FT80X_STENCIL_OP` and `FT80X_STENCIL_FUNC` primitives with a 100-frame bouncing ball animation and click audio effects
- `[ft80x_primitives.c:ft80x_prim_alphablend]` - Demonstrates additive alpha blending using `FT80X_COLOR_A` and `FT80X_PRIM_BITMAPS`
- `[ft80x_coprocessor.c:ft80x_coproc_button]` - Demonstrates the `FT80X_CMD_BUTTON` co-processor widget with flat, 3D, colored, and gradient styles
- `[ft80x_coprocessor.c:ft80x_coproc_clock]` - Demonstrates the `FT80X_CMD_CLOCK` co-processor widget with various options and an optional scaled bitmap background
- `[ft80x_coprocessor.c:ft80x_coproc_gauge]` - Demonstrates the `FT80X_CMD_GAUGE` co-processor widget with various options and an optional scaled bitmap background
- `[ft80x_coprocessor.c:ft80x_coproc_keys]` - Demonstrates the `FT80X_CMD_KEYS` co-processor widget and keyboard layout
- `[ft80x_coprocessor.c:ft80x_coproc_interactive]` - Demonstrates interactive touch input polling (`ft80x_touch_tag`) with `FT80X_CMD_KEYS` over 600 iterations
- `[ft80x_coprocessor.c:ft80x_coproc_progressbar]` - Demonstrates horizontal and vertical `FT80X_CMD_PROGRESS` co-processor widgets
- `[ft80x_coprocessor.c:ft80x_coproc_scrollbar]` - Demonstrates horizontal and vertical `FT80X_CMD_SCROLLBAR` co-processor widgets
- `[ft80x_coprocessor.c:ft80x_coproc_slider]` - Demonstrates horizontal and vertical `FT80X_CMD_SLIDER` co-processor widgets
- `[ft80x_coprocessor.c:ft80x_coproc_dial]` - Demonstrates the `FT80X_CMD_DIAL` rotary control widget
- `[ft80x_coprocessor.c:ft80x_coproc_toggle]` - Demonstrates the `FT80X_CMD_TOGGLE` switch widget
- `[ft80x_coprocessor.c:ft80x_coproc_number]` - Demonstrates the `FT80X_CMD_NUMBER` decimal number widget with alignment and sign options
- `[ft80x_coprocessor.c:ft80x_coproc_calibrate]` - Executes `FT80X_CMD_CALIBRATE` touch calibration and reads back the transform matrix via `ft80x_touch_gettransform`
- `[ft80x_coprocessor.c:ft80x_coproc_spinner]` - Demonstrates `FT80X_CMD_SPINNER` styles 0-3 followed by `FT80X_CMD_STOP`
- `[ft80x_coprocessor.c:ft80x_coproc_screensaver]` - Demonstrates `FT80X_CMD_SCREENSAVER` with `FT80X_MACRO(0)` and `FT80X_CMD_MEMSET`, followed by `FT80X_CMD_STOP`
- `[ft80x_coprocessor.c:ft80x_coproc_logo]` - Plays the FTDI device logo animation via `FT80X_CMD_LOGO` and waits for completion via `ft80x_coproc_waitlogo`

## Invariants
- `[ft80x.h:CONFIG_EXAMPLES_FT80X]` - Entire header declarations and macros in `ft80x.h` are compiled only when `CONFIG_EXAMPLES_FT80X` is defined
- `[ft80x.h:CONFIG_EXAMPLES_FT80X_EXCLUDE_BITMAPS]` - When defined, excludes `g_lenaface_bmhdr`, `ft80x_prim_bitmaps`, `ft80x_coproc_screensaver`, and bitmap-dependent sections in `ft80x_coproc_clock` and `ft80x_coproc_gauge`
- `[ft80x_main.c:g_coproc]` - `ft80x_coproc_calibrate` is ordered first in `g_coproc` so touch calibration runs before `ft80x_coproc_interactive`
- `[ft80x_coprocessor.c:ft80x_coproc_interactive]` - `text` buffer has size `INTERACTIVE_TEXTSIZE` (512), is always NUL-terminated at `text[textndx + 1]`, and `textndx` resets to 0 when `textndx > 24`
- `[ft80x_coprocessor.c:ft80x_coproc_logo]` - During `FT80X_CMD_LOGO` playback, the MCU must not access any FT800 resources until `ft80x_coproc_waitlogo` completes

## Side Effects
- `[ft80x_main.c:main]` - Opens `CONFIG_EXAMPLES_FT80X_DEVPATH` with `O_WRONLY`, dynamically allocates/frees `struct ft80x_dlbuffer_s` on the heap, and closes the file descriptor on exit
- `[ft80x_main.c:ft80x_showname]` - Sets display backlight to 0 via `ft80x_backlight_set`, writes display list commands to FT80x hardware, fades backlight to 100 over 2000 ms via `ft80x_backlight_fade`, and blocks via `sleep(1)`
- `[ft80x_primitives.c:ft80x_prim_bitmaps]` - Writes bitmap data directly into FT80x graphics RAM (`FT80X_RAM_G` offset 0) via `ft80x_ramg_write` and submits hardware display lists
- `[ft80x_primitives.c:ft80x_prim_stencil]` - Enables FT80x audio via `ft80x_audio_enable(fd, true)`, plays `FT08X_EFFECT_CLICK` sound effects via `ft80x_audio_playsound` on boundary collisions, updates display lists for 100 iterations, and disables audio via `ft80x_audio_enable(fd, false)`
- `[ft80x_coprocessor.c:ft80x_coproc_interactive]` - Polls touch tags from hardware via `ft80x_touch_tag(fd)`, updates the display list, and sleeps for 10 ms (`usleep(10 * 1000)`) per iteration for 600 iterations
- `[ft80x_coprocessor.c:ft80x_coproc_calibrate]` - Flushes calibration command to co-processor via `ft80x_dl_flush`, blocks waiting for user touch calibration, and reads transform matrix from hardware via `ft80x_touch_gettransform`

## Verification
- Run: `make test`
