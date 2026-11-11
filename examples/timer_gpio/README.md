# timer_gpio

## Overview
Timer GPIO example (`timer_gpio`). Enable the timer-gpio example. This example uses the timer interrupt to periodically change the state of a digital output. The digital output may be a relay, a led or anything else. This example can be very useful to validate timer drivers by using a logic analyzer connected to the digital output. This example differs from the timer example because it waits on a sigwaitinfo() instead of using a signal handler. This approach ensures a deterministic wake-up time when the signal occurs.

## Interface
- `[Kconfig:EXAMPLES_TIMER_GPIO]` - Build configuration option `EXAMPLES_TIMER_GPIO`
- `[Kconfig:EXAMPLES_TIMER_GPIO_TIM_DEVNAME]` - Build configuration option `EXAMPLES_TIMER_GPIO_TIM_DEVNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_TIMER_GPIO_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_TIMER_GPIO_PROGNAME}`
- `[timer_gpio_main.c:main]` - Application entry point `main()`
- `[timer_gpio_main.c:getopt]` - Command-line option parser supporting flags `":t:g:"`

## Invariants
- `[Kconfig:depends on TIMER && DEV_GPIO]` - Requires kernel/app configuration `TIMER && DEV_GPIO`

## Side Effects
- `[timer_gpio_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[timer_gpio_main.c:open]` - Opens device nodes or files via `open()`
- `[timer_gpio_main.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[timer_gpio_main.c:sigwaitinfo]` - Waits synchronously for signals via `sigwaitinfo()`
- `[timer_gpio_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
