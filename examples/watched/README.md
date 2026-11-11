# watched

## Overview
Watched example (`watched`). This application works with the watcher example and plays the role of the watched task. This process will create 2 watched tasks. These tasks will subscribe to be watched. One task will feed the dog and the other will starve the dog. So, the watchdog timer will expire and the offending task will be printed.

## Interface
- `[Kconfig:EXAMPLES_WATCHED]` - Build configuration option `EXAMPLES_WATCHED`
- `[Kconfig:EXAMPLES_WATCHED_PROGNAME]` - Build configuration option `EXAMPLES_WATCHED_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_WATCHED_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_WATCHED_PROGNAME}`
- `[watched.h:struct watcher_info_s]` - Structure definition `watcher_info_s`
- `[watched.h:struct request_s]` - Structure definition `request_s`
- `[watched.h:struct watched_info_s]` - Structure definition `watched_info_s`
- `[watched.h:watched_is_watcher_on]` - Public function declaration `watched_is_watcher_on()`
- `[watched.h:watched_read_watcher_info]` - Public function declaration `watched_read_watcher_info()`
- `[watched.h:watched_subscribe]` - Public function declaration `watched_subscribe()`
- `[watched.h:watched_unsubscribe]` - Public function declaration `watched_unsubscribe()`
- `[watched.h:watched_feed_dog]` - Public function declaration `watched_feed_dog()`
- `[watched.c:watched_is_watcher_on]` - Public function `watched_is_watcher_on()`
- `[watched.c:watched_read_watcher_info]` - Public function `watched_read_watcher_info()`
- `[watched.c:watched_subscribe]` - Public function `watched_subscribe()`
- `[watched.c:watched_unsubscribe]` - Public function `watched_unsubscribe()`
- `[watched.c:watched_feed_dog]` - Public function `watched_feed_dog()`
- `[watched_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on EXAMPLES_WATCHER]` - Requires kernel/app configuration `EXAMPLES_WATCHER`

## Side Effects
- `[watched.c:/mnt/watcher/info.txt]` - Opens or interacts with VFS/device path `/mnt/watcher/info.txt`
- `[watched.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[watched_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[watched_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
