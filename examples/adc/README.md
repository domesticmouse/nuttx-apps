# adc

## Overview
ADC example (`adc`). Enable the ADC example

## Interface
- `[Kconfig:EXAMPLES_ADC]` - Build configuration option `EXAMPLES_ADC`
- `[Kconfig:EXAMPLES_ADC_DEVPATH]` - Build configuration option `EXAMPLES_ADC_DEVPATH`
- `[Makefile:PROGNAME]` - Registers application/module target `adc`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `adc`
- `[adc.h:struct adc_state_s]` - Structure definition `adc_state_s`
- `[adc_main.c:main]` - Application entry point `main()`

## Invariants
- `[Kconfig:depends on ADC && BOARDCTL]` - Requires kernel/app configuration `ADC && BOARDCTL`
- `[adc.h:#error]` - Compile-time precondition: ADC device support is not enabled (CONFIG_ADC)
- `[adc.h:CONFIG_ADC]` - Configuration guard on `CONFIG_ADC`
- `[adc.h:CONFIG_EXAMPLES_ADC_DEVPATH]` - Configuration guard on `CONFIG_EXAMPLES_ADC_DEVPATH`
- `[adc.h:CONFIG_EXAMPLES_ADC_GROUPSIZE]` - Configuration guard on `CONFIG_EXAMPLES_ADC_GROUPSIZE`
- `[adc_main.c:CONFIG_EXAMPLES_ADC_SWTRIG]` - Configuration guard on `CONFIG_EXAMPLES_ADC_SWTRIG`

## Side Effects
- `[adc.h:/dev/adc0]` - Opens or interacts with VFS/device path `/dev/adc0`
- `[adc_main.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[adc_main.c:open]` - Opens device nodes or files via `open()`
- `[adc_main.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[adc_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
