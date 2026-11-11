# smf

## Overview
State Machine Framework PSICC2 demo (HSM) (`smf`).

## Interface
- `[Kconfig:EXAMPLES_SMF]` - Build configuration option `EXAMPLES_SMF`
- `[Kconfig:EXAMPLES_SMF_PROGNAME]` - Build configuration option `EXAMPLES_SMF_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_SMF_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_SMF_PROGNAME}`
- `[hsm_psicc2_thread.h:struct hsm_psicc2_event]` - Structure definition `hsm_psicc2_event`
- `[hsm_psicc2_thread.h:enum demo_events]` - Enumeration `demo_events`
- `[hsm_psicc2_thread.h:hsm_psicc2_thread_start]` - Public function declaration `hsm_psicc2_thread_start()`
- `[hsm_psicc2_thread.h:hsm_psicc2_post_event]` - Public function declaration `hsm_psicc2_post_event()`
- `[smf_main.c:main]` - Application entry point `main()`
- `[hsm_psicc2_thread.c:struct s_object]` - Structure definition `s_object`
- `[hsm_psicc2_thread.c:enum demo_states]` - Enumeration `demo_states`
- `[hsm_psicc2_thread.c:hsm_psicc2_thread_start]` - Public function `hsm_psicc2_thread_start()`
- `[hsm_psicc2_thread.c:hsm_psicc2_post_event]` - Public function `hsm_psicc2_post_event()`
- `[hsm_psicc2_thread.c:hsm_psicc2_thread_main]` - Application entry point `hsm_psicc2_thread_main()`

## Invariants
- `[Kconfig:depends on NSH_BUILTIN_APPS]` - Requires kernel/app configuration `NSH_BUILTIN_APPS`
- `[Kconfig:depends on SYSTEM_SMF]` - Requires kernel/app configuration `SYSTEM_SMF`
- `[Kconfig:depends on SYSTEM_SMF_ANCESTOR_SUPPORT]` - Requires kernel/app configuration `SYSTEM_SMF_ANCESTOR_SUPPORT`
- `[smf_main.c:argc]` - Validates command-line argument count `argc`

## Side Effects
- `[smf_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[hsm_psicc2_thread.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[hsm_psicc2_thread.c:mq_open]` - Opens POSIX message queues via `mq_open()`
- `[hsm_psicc2_thread.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
