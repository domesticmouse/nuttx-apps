# `include/system`

## Overview
Implements `include/system`: EMACS-like command line editor. This is actually more like readline than is the NuttX readline!

## Interface
- [cle.h:cle_fd]
- [cle.h:cle]
- [fastboot.h:fastboot_handler]
- [microros_transport.h:microros_transport_init]
- [nxcamera.h:struct nxcamera_s]
- [nxcamera.h:struct video_msg_s]
- [nxcamera.h:u]
- [nxcamera.h:nxcamera_create]
- [nxcamera.h:nxcamera_release]
- [nxcamera.h:nxcamera_reference]
- [nxcamera.h:nxcamera_stream]
- [nxcamera.h:nxcamera_stop]
- [nxcamera.h:nxcamera_setdevice]
- [nxcamera.h:nxcamera_setfb]
- [nxcamera.h:nxcamera_setfile]
- [nxcamera.h:nxcamera_ioctl]
- [nxlooper.h:struct nxlooper_s]
- [nxlooper.h:nxlooper_create]

## Invariants
- [cle.h:CONFIG_SYSTEM_CLE]: Conditional compilation gated by `CONFIG_SYSTEM_CLE`.
- [cle.h:CONFIG_FILE_STREAM]: Conditional compilation gated by `CONFIG_FILE_STREAM`.
- [nxcamera.h:CONFIG_LIBYUV]: Conditional compilation gated by `CONFIG_LIBYUV`.
- [nxlooper.h:CONFIG_AUDIO_MULTI_SESSION]: Conditional compilation gated by `CONFIG_AUDIO_MULTI_SESSION`.
- [nxlooper.h:CONFIG_AUDIO_EXCLUDE_VOLUME]: Conditional compilation gated by `CONFIG_AUDIO_EXCLUDE_VOLUME`.
- [nxlooper.h:CONFIG_AUDIO_EXCLUDE_STOP]: Conditional compilation gated by `CONFIG_AUDIO_EXCLUDE_STOP`.

## Side Effects
- None

## Verification
- Run: `make test`
