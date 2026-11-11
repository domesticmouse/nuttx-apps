# `system/zbus`

## Overview
Provides ZBus message bus library (`system/zbus`). Enable the zbus message bus library (port of the Zephyr zbus). Channels and observers are defined statically with the

## Interface
- [Kconfig:CONFIG_ZBUS]
- [Kconfig:CONFIG_ZBUS_CHANNEL_NAME]
- [Kconfig:CONFIG_ZBUS_CHANNEL_ID]
- [Kconfig:CONFIG_ZBUS_OBSERVER_NAME]
- [zbus_priv.h:enum zbus_deadline_mode_e]
- [zbus_priv.h:struct zbus_deadline]
- [zbus_priv.h:zbus_port_init_once]
- [zbus_priv.h:zbus_deadline_init]
- [zbus_priv.h:zbus_sem_take]
- [zbus.c:zbus_port_init_once]
- [zbus.c:zbus_deadline_init]
- [zbus.c:zbus_sem_take]
- [zbus.c:zbus_chan_pub]
- [zbus.c:zbus_chan_read]
- [zbus.c:zbus_chan_notify]
- [zbus.c:zbus_chan_claim]
- [zbus.c:zbus_chan_finish]
- [zbus.c:zbus_sub_wait]

## Invariants
- [Kconfig:CONFIG_ZBUS]: Build and feature compilation gated by `CONFIG_ZBUS`.
- [Kconfig:CONFIG_ZBUS_CHANNEL_NAME]: Build and feature compilation gated by `CONFIG_ZBUS_CHANNEL_NAME`.
- [Kconfig:depends on !DISABLE_MQUEUE]: Requires Kconfig dependency condition `!DISABLE_MQUEUE`.
- [Kconfig:depends on ZBUS_MSG_SUBSCRIBER]: Requires Kconfig dependency condition `ZBUS_MSG_SUBSCRIBER`.
- [zbus.c:sem_wait]: Synchronizes concurrent access across threads or critical sections.
- [zbus.c:pthread_mutex_lock]: Synchronizes concurrent access across threads or critical sections.

## Side Effects
- [zbus.c:task_create]: Spawns child tasks, pthreads, or built-in applications.
- [zbus.c:syslog]: Writes formatted diagnostic, logging, or console output.
- [zbus_runtime_observers.c:malloc]: Allocates or releases dynamic heap memory.

## Verification
- Run: `make test`
