# `industry/cnc/nvmpg-dro`

## Overview
Provides Digital Dream NVMPG pendant DRO (`industry/cnc/nvmpg-dro`). Digital readout firmware for the Digital Dream NVMPG pendant used with the NVUM/NVEM/EC300/EC500 CNC motion controllers. It shows

## Interface
- [Makefile:PROGNAME=$(CONFIG_INDUSTRY_CNC_NVMPG_DRO_PROGNAME)]
- [Kconfig:CONFIG_INDUSTRY_CNC_NVMPG_DRO]
- [Kconfig:CONFIG_INDUSTRY_CNC_NVMPG_DRO_PROGNAME]
- [Kconfig:CONFIG_INDUSTRY_CNC_NVMPG_DRO_PRIORITY]
- [Kconfig:CONFIG_INDUSTRY_CNC_NVMPG_DRO_STACKSIZE]
- [nvmpg_dro.h:nvdro_lcd_open]
- [nvmpg_dro.h:nvdro_lcd_close]
- [nvmpg_dro.h:nvdro_lcd_width]
- [nvmpg_dro.h:nvdro_lcd_height]
- [nvmpg_dro.h:nvdro_fill]
- [nvmpg_dro.h:nvdro_putrow]
- [nvmpg_dro.h:nvdro_frame]
- [nvmpg_dro.h:nvdro_text]
- [nvmpg_dro.h:nvdro_text_width]
- [nvmpg_dro.h:nvdro_logo]
- [nvmpg_dro_lcd.c:nvdro_lcd_open]
- [nvmpg_dro_lcd.c:nvdro_lcd_close]
- [nvmpg_dro_lcd.c:nvdro_lcd_width]

## Invariants
- [Kconfig:CONFIG_INDUSTRY_CNC_NVMPG_DRO]: Build and feature compilation gated by `CONFIG_INDUSTRY_CNC_NVMPG_DRO`.
- [Kconfig:CONFIG_INDUSTRY_CNC_NVMPG_DRO_PROGNAME]: Build and feature compilation gated by `CONFIG_INDUSTRY_CNC_NVMPG_DRO_PROGNAME`.
- [Kconfig:depends on LCD_DEV && DEV_GPIO && !DISABLE_PTHREAD]: Requires Kconfig dependency condition `LCD_DEV && DEV_GPIO && !DISABLE_PTHREAD`.
- [Kconfig:depends on INDUSTRY_CNC_NVMPG_DRO_SPLASH]: Requires Kconfig dependency condition `INDUSTRY_CNC_NVMPG_DRO_SPLASH`.
- [nvmpg_dro.h:CONFIG_INDUSTRY_CNC_NVMPG_DRO_SPLASH]: Conditional compilation gated by `CONFIG_INDUSTRY_CNC_NVMPG_DRO_SPLASH`.
- [nvmpg_dro_main.c:pthread_mutex_lock]: Synchronizes concurrent access across threads or critical sections.

## Side Effects
- [nvmpg_dro_lcd.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [nvmpg_dro_lcd.c:open]: Performs VFS file or device descriptor I/O operations.
- [nvmpg_dro_main.c:ioctl]: Issues device/driver control requests via `ioctl()`.
- [nvmpg_dro_main.c:write]: Performs VFS file or device descriptor I/O operations.
- [nvmpg_dro_main.c:pthread_create]: Spawns child tasks, pthreads, or built-in applications.
- [nvmpg_dro_main.c:syslog]: Writes formatted diagnostic, logging, or console output.

## Verification
- Run: `make test`
