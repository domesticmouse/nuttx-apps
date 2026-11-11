# pwm

## Overview
Pulse width modulation (PWM) example (`pwm`). Enable the Pulse width modulation (PWM) example

## Interface
- `[Kconfig:EXAMPLES_PWM]` - Build configuration option `EXAMPLES_PWM`
- `[Kconfig:EXAMPLES_PWM_DEVPATH]` - Build configuration option `EXAMPLES_PWM_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `pwm`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `pwm`
- `[pwm_main.c:struct pwm_state_s]` - Structure definition `pwm_state_s`
- `[pwm_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on PWM]` - Requires kernel/app configuration `PWM`
- `[pwm.h:#error]` - Compile-time precondition: PWM device support is not enabled (CONFIG_PWM)
- `[pwm.h:CONFIG_PWM]` - Configuration guard on `CONFIG_PWM`
- `[pwm.h:CONFIG_EXAMPLES_PWM_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_PWM_DEVPATH`
- `[pwm.h:CONFIG_EXAMPLES_PWM_FREQUENCY]` - Configuration guard on `CONFIG_EXAMPLES_PWM_FREQUENCY`
- `[pwm.h:CONFIG_EXAMPLES_PWM_DURATION]` - Configuration guard on `CONFIG_EXAMPLES_PWM_DURATION`
- `[pwm_main.c:#error]` - Compile-time precondition: Channel numbers must be unique
- `[pwm_main.c:#error]` - Compile-time precondition: Too many PWM channels
- `[pwm_main.c:CONFIG_PWM_NCHANNELS]` - Configuration guard on `CONFIG_PWM_NCHANNELS`
- `[pwm_main.c:CONFIG_EXAMPLES_PWM_CHANNEL1]` - Configuration guard on `CONFIG_EXAMPLES_PWM_CHANNEL1`

## Side Effects
- `[pwm.h:/dev/pwm0]` - Opens or interacts with VFS/device path `/dev/pwm0`
- `[pwm_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[pwm_main.c:open]` - Opens device nodes or files via `open()`
- `[pwm_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
