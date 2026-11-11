# foc

## Overview
FOC motor controller example (`foc`). Enable the FOC motor controller example. At the moment, this example implements a simple open-loop velocity controller.

## Interface
- `[foc_main.c:main]` - Entry point for the FOC example application; parses/validates args, initializes NxScope, threads, and user interfaces, spawns per-instance FOC control threads, and runs the 200ms auxiliary loop
- `[foc_cfg.h:struct foc_thr_cfg_s]` - Structure defining control thread configuration parameters (`fmode`, `mmode`, open-loop settings, PI gains, torque/vel/pos limits, ramp acc/dec, motor ident settings, and observer parameters)
- `[foc_device.h:struct foc_device_s]` - Structure representing a FOC hardware device instance (`fd`, `info`, `state`, `params`, and optional perf stats)
- `[foc_device.c:foc_device_init]` - Opens the FOC character device (`/dev/focN`), queries device info, and applies PWM and notifier frequencies
- `[foc_device.c:foc_device_deinit]` - Stops the FOC device via `foc_dev_stop` and closes its file descriptor
- `[foc_device.c:foc_device_start]` - Starts or stops the FOC device via `foc_dev_start` or `foc_dev_stop`
- `[foc_device.c:foc_dev_state_get]` - Performs a blocking read of the FOC device state via `foc_dev_getstate`
- `[foc_device.c:foc_dev_params_set]` - Writes updated FOC duty/parameters to the device via `foc_dev_setparams`
- `[foc_device.c:foc_dev_state_handle]` - Checks `dev->state.fault`, sets the fault flag, and clears device faults via `foc_dev_clearfault`
- `[foc_intf.c:foc_intf_init]` - Initializes configured user input interfaces (ADC, button, and/or stdin character control)
- `[foc_intf.c:foc_intf_update]` - Polls configured user input interfaces and updates `struct foc_intf_data_s`
- `[foc_mq.c:foc_mq_handle]` - Non-blocking receive on a POSIX message queue that decodes 5-byte control messages into `struct foc_mq_s`
- `[foc_parseargs.c:parse_args]` - Parses command-line options via `getopt_long` into `struct args_s`
- `[foc_parseargs.c:validate_args]` - Validates parsed arguments (PI gains, `fmode`, `mmode`, `state`, `time`, and motor identification parameters)
- `[foc_thr.c:foc_ctrlthr_init]` - Creates the per-instance POSIX message queue and spawns the real-time FOC control pthread
- `[foc_fixed16_thr.c:foc_fixed16_thr]` - Main real-time control loop function for fixed16 (`b16_t`) FOC instances
- `[foc_float_thr.c:foc_float_thr]` - Main real-time control loop function for `float32` FOC instances
- `[foc_motor_b16.c:foc_motor_init]` - Initializes fixed16 motor state, angle/velocity observers or sensors, PI controllers, and align/ident routines
- `[foc_motor_b16.c:foc_motor_control]` - Steps the fixed16 motor controller state machine (`INIT`, `ALIGN`, `IDENT`, `RUN_INIT`, `RUN`, `IDLE`, `TERMINATE`)
- `[foc_motor_f32.c:foc_motor_init]` - Initializes float32 motor state, angle/velocity observers or sensors, PI controllers, and align/ident routines
- `[foc_motor_f32.c:foc_motor_control]` - Steps the float32 motor controller state machine
- `[foc_nxscope.c:foc_nxscope_init]` - Initializes NxScope serial transport, protocol, channels for each FOC instance, and optional worker thread
- `[foc_perf.c:foc_perf_end]` - Computes control cycle execution time and period and updates maximums

## Invariants
- `[foc_cfg.h:CONFIG_EXAMPLES_FOC_SENSORLESS]` - Cannot be enabled simultaneously with `CONFIG_EXAMPLES_FOC_SENSORED`; requires `CONFIG_EXAMPLES_FOC_HAVE_VEL` and `CONFIG_EXAMPLES_FOC_HAVE_OPENLOOP`
- `[foc_cfg.h:CONFIG_EXAMPLES_FOC_CONTROL_PI]` - Must be defined; only the FOC PI current controller is supported
- `[foc_adc.h:CONFIG_ADC_FIFOSIZE]` - When `CONFIG_EXAMPLES_FOC_HAVE_ADC` is enabled, `CONFIG_ADC_FIFOSIZE` must equal `(ADC_SAMPLES + 1)`
- `[foc_parseargs.c:validate_args]` - Enforces non-zero Kp/Ki gains, valid `fmode` (`1..3`), valid `mmode`, valid `state` (`1..4`), `time` (`> 0` or `-1`), and non-zero motor ident parameters
- `[foc_mq.c:foc_mq_handle]` - Requires received POSIX message length to equal `CONTROL_MQ_MSGSIZE` (5 bytes) and message type in `1..5`

## Side Effects
- `[foc_device.c:foc_device_init]` - Opens `/dev/focN` and performs device ioctls via `foc_dev_getinfo` and `foc_dev_setcfg`
- `[foc_device.c:foc_device_start]` - Starts/stops PWM/FOC hardware via `foc_dev_start` and `foc_dev_stop` ioctls
- `[foc_intf.c:foc_adc_init]` - Opens `CONFIG_EXAMPLES_FOC_ADC_DEVPATH` and issues `ANIOC_TRIGGER` ioctl
- `[foc_thr.c:foc_ctrlthr_init]` - Creates/opens POSIX message queues (`mqfN`) and spawns real-time control pthreads
- `[foc_fixed16_thr.c:foc_enter_critical]` - Disables interrupts via `enter_critical_section()` / `leave_critical_section()` when `CONFIG_EXAMPLES_FOC_CONTROL_CRITSEC` is enabled
- `[foc_nxscope.c:foc_nxscope_init]` - Opens serial port `CONFIG_EXAMPLES_FOC_NXSCOPE_SERIAL_PATH` and transmits telemetry data over the NxScope interface

## Verification
- Run: `make test`
