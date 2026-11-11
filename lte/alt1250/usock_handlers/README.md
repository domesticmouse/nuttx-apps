# `lte/alt1250/usock_handlers`

## Overview
Implements `lte/alt1250/usock_handlers` source and header components (`alt1250_accepthdlr.c`, `alt1250_bindhdlr.c`, `alt1250_closehdlr.c`, `alt1250_connecthdlr.c` and 24 more files) in the NuttX application tree.

## Interface
- [alt1250_fwupdate.h:struct delta_header_s]
- [alt1250_fwupdate.h:struct update_info_s]
- [alt1250_fwupdate.h:LTE_IMAGE_PERT_SIZE]
- [alt1250_ioctl_subhdlr.h:usockreq_ioctl_ltecmd]
- [alt1250_ioctl_subhdlr.h:usockreq_ioctl_ifreq]
- [alt1250_ioctl_subhdlr.h:usockreq_ioctl_normal]
- [alt1250_ioctl_subhdlr.h:usockreq_ioctl_event]
- [alt1250_ioctl_subhdlr.h:usockreq_ioctl_other]
- [alt1250_ioctl_subhdlr.h:usockreq_ioctl_power]
- [alt1250_ioctl_subhdlr.h:usockreq_ioctl_fwupdate]
- [alt1250_ioctl_subhdlr.h:usockreq_ioctl_denyinetsock]
- [alt1250_ioctl_subhdlr.h:send_m2mnotice_command]
- [alt1250_ioctl_subhdlr.h:usockreq_ioctl_lwm2m]
- [alt1250_sms.h:enum sms_state_e]
- [alt1250_sms.h:struct sms_info_s]
- [alt1250_sms.h:alt1250_sms_init]
- [alt1250_sms.h:alt1250_sms_fin]
- [alt1250_sms.h:alt1250_sms_send]

## Invariants
- [alt1250_sms.h:CONFIG_LTE_ALT1250_SMS_TOA]: Conditional compilation gated by `CONFIG_LTE_ALT1250_SMS_TOA`.
- [alt1250_ioctl_event.c:CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE]: Conditional compilation gated by `CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE`.
- [alt1250_ioctl_ltecmd.c:CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE]: Conditional compilation gated by `CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE`.
- [alt1250_ioctl_ltecmd.c:CONFIG_LTE_ALT1250_EXTEND_IOCTL]: Conditional compilation gated by `CONFIG_LTE_ALT1250_EXTEND_IOCTL`.
- [alt1250_ioctl_normal.c:CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE]: Conditional compilation gated by `CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE`.
- [alt1250_ioctl_other.c:CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE]: Conditional compilation gated by `CONFIG_LTE_ALT1250_ENABLE_HIBERNATION_MODE`.

## Side Effects
- None

## Verification
- Run: `make test`
