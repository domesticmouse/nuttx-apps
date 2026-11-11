# NuttX Audio Helper Library (`audioutils/nxaudio`)

## Overview
Provides a user-space audio playback helper library (`CONFIG_AUDIOUTILS_NXAUDIO_LIB`) that wraps NuttX `/dev/audio/*` character device `ioctl` operations, POSIX message queue signaling, and audio buffer lifecycle management.

## Interface
- `[nxaudio.c:init_nxaudio]` / `[nxaudio.c:init_nxaudio_devname]`: Opens and configures an audio device (`struct nxaudio_s`), allocates audio buffers, and registers a POSIX message queue.
- `[nxaudio.c:fin_nxaudio]`: Shuts down playback, unregisters and unlinks the message queue, frees audio buffers, and closes descriptors.
- `[nxaudio.c:nxaudio_enqbuffer]`: Enqueues an `struct ap_buffer_s` PCM buffer to the audio driver via `AUDIOIOC_ENQUEUEBUFFER`.
- `[nxaudio.c:nxaudio_start]` / `[nxaudio.c:nxaudio_stop]` / `[nxaudio.c:nxaudio_pause]` / `[nxaudio.c:nxaudio_resume]`: Controls audio playback state via driver `ioctl` calls and stop messages.
- `[nxaudio.c:nxaudio_setvolume]`: Sets audio playback volume (0..1000) via `AUDIOIOC_CONFIGURE`.
- `[nxaudio.c:nxaudio_msgloop]`: Runs the blocking `mq_receive` event loop, invoking caller-supplied buffer dequeue, completion, and user callbacks.
- `[Kconfig:CONFIG_AUDIOUTILS_NXAUDIO_LIB]`, `[Kconfig:CONFIG_AUDIOUTILS_NXAUDIO_DEVPATH]`, `[Kconfig:CONFIG_AUDIOUTILS_NXAUDIO_MSGQNAME]`: Build and default device/queue path configuration options.

## Invariants
- `[nxaudio.c:nxaudio_msgloop]`: Returns `-1` immediately if `cbs == NULL`; ignores dequeued messages whose `mq_receive` byte count does not equal `sizeof(struct audio_msg_s)`.

## Side Effects
- `[nxaudio.c:init_nxaudio_devname]`: Opens the target audio device descriptor, issues `AUDIOIOC_RESERVE`, `AUDIOIOC_CONFIGURE`, `AUDIOIOC_GETBUFFERINFO`, `AUDIOIOC_ALLOCBUFFER`, and `AUDIOIOC_REGISTERMQ` `ioctl` calls, creates a POSIX message queue via `mq_open`, and allocates the buffer pointer array via `calloc`.
- `[nxaudio.c:fin_nxaudio]`: Issues `AUDIOIOC_SHUTDOWN`, `AUDIOIOC_UNREGISTERMQ`, `AUDIOIOC_RELEASE`, and `AUDIOIOC_FREEBUFFER` `ioctl` calls, frees `nxaudio->abufs`, closes `nxaudio->fd` and `nxaudio->mq`, and unlinks `CONFIG_AUDIOUTILS_NXAUDIO_MSGQNAME` via `mq_unlink`.
- `[nxaudio.c:nxaudio_enqbuffer]`, `[nxaudio.c:nxaudio_start]`, `[nxaudio.c:nxaudio_stop]`, `[nxaudio.c:nxaudio_pause]`, `[nxaudio.c:nxaudio_resume]`, and `[nxaudio.c:nxaudio_setvolume]`: Issue corresponding `AUDIOIOC_*` `ioctl` commands and send `AUDIO_MSG_STOP` over `nxaudio->mq`.

## Verification
- Run: `make test`
