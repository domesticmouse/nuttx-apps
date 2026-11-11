# watcher

## Overview
Watcher example (`watcher`). Enable the watcher example. The watcher is a task that will monitor other tasks that have previously subscribed to be watched. If the watched tasks don't signal the watcher during the watchdog time period, the watchdog timer will expire and the watcher will print the tasks that did not signal and the ones that signaled. This example will only be supported by the chips that supports interrupt on timeout, i.e., which have the "capture" command implemented.

## Interface
- `[Kconfig:EXAMPLES_WATCHER]` - Build configuration option `EXAMPLES_WATCHER`
- `[Kconfig:EXAMPLES_WATCHER_PROGNAME]` - Build configuration option `EXAMPLES_WATCHER_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_WATCHER_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_WATCHER_PROGNAME}`
- `[ramdisk.h:create_ramdisk]` - Public function declaration `create_ramdisk()`
- `[ramdisk.h:prepare_fs]` - Public function declaration `prepare_fs()`
- `[task_mn.h:struct request_s]` - Structure definition `request_s`
- `[task_mn.h:struct task_node_s]` - Structure definition `task_node_s`
- `[task_mn.h:struct task_list_s]` - Structure definition `task_list_s`
- `[task_mn.h:task_mn_print_tasks_status]` - Public function declaration `task_mn_print_tasks_status()`
- `[task_mn.h:task_mn_reset_all]` - Public function declaration `task_mn_reset_all()`
- `[task_mn.h:task_mn_is_task_subscribed]` - Public function declaration `task_mn_is_task_subscribed()`
- `[task_mn.h:task_mn_add_to_list]` - Public function declaration `task_mn_add_to_list()`
- `[task_mn.h:task_mn_remove_from_list]` - Public function declaration `task_mn_remove_from_list()`
- `[task_mn.h:task_mn_subscribe]` - Public function declaration `task_mn_subscribe()`
- `[task_mn.h:task_mn_unsubscribe]` - Public function declaration `task_mn_unsubscribe()`
- `[task_mn.h:task_mn_all_tasks_fed]` - Public function declaration `task_mn_all_tasks_fed()`
- `[wdt.h:struct wdog_params_s]` - Structure definition `wdog_params_s`
- `[wdt.h:wdt_init]` - Public function declaration `wdt_init()`
- `[wdt.h:wdt_feed_the_dog]` - Public function declaration `wdt_feed_the_dog()`
- `[watcher_main.c:main]` - Application entry point `main()`
- `[ramdisk.c:create_ramdisk]` - Public function `create_ramdisk()`
- `[ramdisk.c:prepare_fs]` - Public function `prepare_fs()`
- `[task_mn.c:task_mn_print_tasks_status]` - Public function `task_mn_print_tasks_status()`
- `[task_mn.c:task_mn_reset_all]` - Public function `task_mn_reset_all()`
- `[task_mn.c:task_mn_is_task_subscribed]` - Public function `task_mn_is_task_subscribed()`
- `[task_mn.c:task_mn_add_to_list]` - Public function `task_mn_add_to_list()`
- `[task_mn.c:task_mn_remove_from_list]` - Public function `task_mn_remove_from_list()`
- `[task_mn.c:task_mn_subscribe]` - Public function `task_mn_subscribe()`
- `[task_mn.c:task_mn_unsubscribe]` - Public function `task_mn_unsubscribe()`
- `[task_mn.c:task_mn_all_tasks_fed]` - Public function `task_mn_all_tasks_fed()`
- `[wdt.c:struct wdt_loginfo_s]` - Structure definition `wdt_loginfo_s`
- `[wdt.c:wdt_init]` - Public function `wdt_init()`
- `[wdt.c:wdt_feed_the_dog]` - Public function `wdt_feed_the_dog()`

## Invariants
- `[Kconfig:depends on DRIVERS_NOTERAM]` - Requires kernel/app configuration `DRIVERS_NOTERAM`
- `[Kconfig:depends on FSUTILS_MKFATFS]` - Requires kernel/app configuration `FSUTILS_MKFATFS`

## Side Effects
- `[ramdisk.h:/dev/ram]` - Opens or interacts with VFS/device path `/dev/ram`
- `[watcher_main.c:/mnt/watcher/info.txt]` - Opens or interacts with VFS/device path `/mnt/watcher/info.txt`
- `[watcher_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[watcher_main.c:sigaction]` - Registers signal handlers via `sigaction()`
- `[watcher_main.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[watcher_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[ramdisk.c:/mnt/watcher]` - Opens or interacts with VFS/device path `/mnt/watcher`
- `[ramdisk.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[ramdisk.c:mount]` - Mounts filesystems via `mount()`
- `[ramdisk.c:printf]` - Writes formatted output to standard output via `printf()`
- `[task_mn.c:/dev/note/ram]` - Opens or interacts with VFS/device path `/dev/note/ram`
- `[task_mn.c:open]` - Opens device nodes or files via `open()`
- `[task_mn.c:printf]` - Writes formatted output to standard output via `printf()`
- `[wdt.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[wdt.c:open]` - Opens device nodes or files via `open()`
- `[wdt.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
