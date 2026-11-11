# pdcurses

## Overview
pdcurses demos (`pdcurses`). Enable build the pdcurses demo programs

## Interface
- `[charset_main.c:main]` - Entry point for the PDCurses character set display example
- `[firework_main.c:main]` - Entry point for the PDCurses animated fireworks example
- `[newdemo_main.c:main]` - Entry point for the PDCurses window, subwindow, scrolling message, and bouncing balls demo
- `[panel_main.c:main]` - Entry point for the PDCurses panel library demonstration (accepts optional delay in ms via `argv[1]`)
- `[rain_main.c:main]` - Entry point for the PDCurses animated raindrop example
- `[testcurs_main.c:main]` - Entry point for the interactive PDCurses test suite (intro, pad, resize, scroll, input, output, ACS, color, clipboard, wide char tests)
- `[testcurs_main.c:display_menu]` - Renders the main test selection menu on `stdscr`
- `[tui.h:FUNC]` - Function pointer typedef `void (*FUNC)(void)` for TUI menu callbacks
- `[tui.h:struct menu]` - Structure `{ char *name; FUNC func; char *desc; }` defining a TUI menu item
- `[tui.c:clsbody]` - Clears and resets cursor to (0,0) in the TUI body window (`wbody`)
- `[tui.c:bodylen]` - Returns the height (`getmaxy`) of the TUI body window (`wbody`)
- `[tui.c:bodywin]` - Returns the `WINDOW *` pointer to the TUI body window (`wbody`)
- `[tui.c:rmerror]` - Clears the error message line (line 0) in the status window (`wstat`)
- `[tui.c:rmstatus]` - Clears the status message line (line 1) in the status window (`wstat`)
- `[tui.c:titlemsg]` - Displays a padded string in the title window (`wtitl`)
- `[tui.c:bodymsg]` - Appends a string to the body window (`wbody`) and refreshes it
- `[tui.c:errormsg]` - Emits `beep()` and displays an error string on line 0 of `wstat`
- `[tui.c:statusmsg]` - Displays a status string on line 1 of `wstat`
- `[tui.c:keypressed]` - Polls `wgetch(wbody)` into static `ch` and returns true if a key was read (`ch != ERR`)
- `[tui.c:getkey]` - Consumes and returns the cached key `ch`
- `[tui.c:waitforkey]` - Loops calling `idle()` until `keypressed()` is true, then returns `getkey()`
- `[tui.c:tui_exit]` - Sets static `quit = true` to terminate the TUI menu loop
- `[tui.c:domenu]` - Creates a boxed submenu window and runs its interactive selection loop
- `[tui.c:startmenu]` - Initializes curses, creates TUI layout subwindows (`wtitl`, `wmain`, `wbody`, `wstat`), runs `mainmenu(mp)`, and cleans up on exit
- `[tui.c:weditstr]` - Interactive single-line string editor in a subwindow of width `field`
- `[tui.c:winputbox]` - Creates and renders a boxed input window of size `nlines` x `ncols`
- `[tui.c:getstrings]` - Renders a multi-field labeled dialog box in `wbody` and edits each `buf[i]` via `mvweditstr`
- `[tui_main.c:main]` - Entry point for the TUI demonstration program
- `[worm_main.c:main]` - Entry point for the PDCurses animated worms example (supports `-f`, `-l <length>`, `-n <number>`, `-t` options)
- `[xmas_main.c:main]` - Entry point for the PDCurses animated Christmas greeting card example

## Invariants
- `[charset_main.c:main]` - Printable character range is bounded by `FIRST_CH` (0x20) through `LAST_CH` (0x7e); grid width is capped at `COLS - 2` and `NUM_CH`, and height is capped at `LINES`
- `[firework_main.c:main]` - Firework launch `start` and `end` columns are clamped to `[2, COLS - 4]` with trajectory `diff = abs(start - end)` constrained to `2 <= diff < LINES - 2`
- `[newdemo_main.c:main]` - Requires a 48x15 window (`newwin`); exits with code 1 if allocation fails
- `[panel_main.c:mkpanel]` - If `new_panel(win)` fails, the newly allocated `WINDOW *win` is immediately freed via `delwin(win)` before returning `NULL`
- `[tui.c:menudim]` - All `menu` arrays passed to `startmenu` or `domenu` must be terminated by a sentinel element where `func == NULL`
- `[tui.c:weditstr]` - Rejects calls with `ERR` if `field >= MAXSTRLEN` (256), `buf == NULL`, or `strlen(buf) > field - 1`
- `[worm_main.c:main]` - CLI worm `length` (`-l`) must be in `[2, 1024]` and worm `number` (`-n`) must be in `[1, 40]`

## Side Effects
- `[charset_main.c:main]` - Enables curses tracing (`traceon()`), initializes terminal screen and color pairs, renders characters to `stdscr`, and calls `endwin()`
- `[firework_main.c:main]` - Seeds PRNG (`srand(time(NULL))`), initializes curses in non-blocking mode (`nodelay`), animates fireworks with `napms(200)` delays, and calls `endwin()`
- `[testcurs_main.c:main]` - Sets locale (`setlocale`), initializes curses, mutates mouse tracking (`mouse_set`) and key modifier flags, resizes/restores terminal (`savetty`, `resize_term`, `resetty`), and emits terminal `beep()`/`flash()`
- `[tui.c:startmenu]` - Initializes curses, allocates module-global subwindows (`wtitl`, `wmain`, `wbody`, `wstat`), mutates static state, and destroys subwindows/calls `endwin()` in `cleanup()`
- `[tui_main.c:showfile]` - Opens and reads local filesystem path (`fopen`, `fgets`, `fclose`) to display file contents in `wbody`
- `[worm_main.c:main]` - Allocates and reallocates 2D `ref` grid and per-worm `xpos`/`ypos` arrays on the heap (`malloc`/`realloc`/`free`), animates worms on `stdscr`, and calls `endwin()`

## Verification
- Run: `make test`
