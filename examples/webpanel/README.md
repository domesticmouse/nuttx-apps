# webpanel

## Overview
Web Panel for device management (`webpanel`). Enable the Web Panel application, a Tasmota-inspired web interface for NuttX devices. Provides a landing page served via THTTPD from ROMFS, CGI handlers for system info, file management, and a WebSocket-based NSH terminal (powered by libwebsockets).

## Interface
- `[Kconfig:EXAMPLES_WEBPANEL]` - Build configuration option `EXAMPLES_WEBPANEL`
- `[Kconfig:EXAMPLES_WEBPANEL_PROGNAME]` - Build configuration option `EXAMPLES_WEBPANEL_PROGNAME`
- `[Makefile:PROGNAME]` - Registers application/module target `$(CONFIG_EXAMPLES_WEBPANEL_PROGNAME)`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `${CONFIG_EXAMPLES_WEBPANEL_PROGNAME}`
- `[ws_terminal.h:ws_terminal_start]` - Public function declaration `ws_terminal_start()`
- `[webpanel_main.c:main]` - Application entry point `main()`
- `[cgi_files.c:files_main]` - Application entry point `files_main()`
- `[cgi_renew.c:dhcprenew_main]` - Application entry point `dhcprenew_main()`
- `[cgi_sysinfo.c:sysinfo_main]` - Application entry point `sysinfo_main()`
- `[cgi_upload.c:upload_main]` - Application entry point `upload_main()`
- `[ws_terminal.c:struct ws_session]` - Structure definition `ws_session`
- `[ws_terminal.c:ws_terminal_start]` - Public function `ws_terminal_start()`

## Invariants
- `[Kconfig:depends on NET_TCP]` - Requires kernel/app configuration `NET_TCP`
- `[Kconfig:depends on NETUTILS_THTTPD]` - Requires kernel/app configuration `NETUTILS_THTTPD`
- `[Kconfig:depends on NETUTILS_LIBWEBSOCKETS]` - Requires kernel/app configuration `NETUTILS_LIBWEBSOCKETS`
- `[ws_terminal.c:CONFIG_EXAMPLES_WEBPANEL_WS_PORT]` - Configuration guard on `CONFIG_EXAMPLES_WEBPANEL_WS_PORT`
- `[ws_terminal.c:CONFIG_EXAMPLES_WEBPANEL_WS_PRIORITY]` - Configuration guard on `CONFIG_EXAMPLES_WEBPANEL_WS_PRIORITY`
- `[ws_terminal.c:CONFIG_EXAMPLES_WEBPANEL_WS_STACKSIZE]` - Configuration guard on `CONFIG_EXAMPLES_WEBPANEL_WS_STACKSIZE`
- `[ws_terminal.c:CONFIG_EXAMPLES_WEBPANEL_WS_NSH_STACKSIZE]` - Configuration guard on `CONFIG_EXAMPLES_WEBPANEL_WS_NSH_STACKSIZE`

## Side Effects
- `[webpanel_main.c:/dev/ram2]` - Opens or interacts with VFS/device path `/dev/ram2`
- `[webpanel_main.c:/dev/smart0]` - Opens or interacts with VFS/device path `/dev/smart0`
- `[webpanel_main.c:boardctl]` - Invokes board-level control operations via `boardctl()`
- `[webpanel_main.c:mount]` - Mounts filesystems via `mount()`
- `[webpanel_main.c:printf]` - Writes formatted output to standard output via `printf()`
- `[cgi_files.c:printf]` - Writes formatted output to standard output via `printf()`
- `[cgi_renew.c:printf]` - Writes formatted output to standard output via `printf()`
- `[cgi_sysinfo.c:/proc/version]` - Opens or interacts with VFS/device path `/proc/version`
- `[cgi_sysinfo.c:ioctl]` - Issues device driver control commands via `ioctl()`
- `[cgi_sysinfo.c:socket]` - Allocates network or IPC socket descriptors via `socket()`
- `[cgi_sysinfo.c:fopen]` - Opens standard I/O file streams via `fopen()`
- `[cgi_sysinfo.c:printf]` - Writes formatted output to standard output via `printf()`
- `[cgi_upload.c:open]` - Opens device nodes or files via `open()`
- `[cgi_upload.c:read]` - Reads bytes from file or device descriptors via `read()`
- `[cgi_upload.c:write]` - Writes bytes to file or device descriptors via `write()`
- `[cgi_upload.c:printf]` - Writes formatted output to standard output via `printf()`
- `[ws_terminal.c:/dev/ptmx]` - Opens or interacts with VFS/device path `/dev/ptmx`
- `[ws_terminal.c:open]` - Opens device nodes or files via `open()`
- `[ws_terminal.c:task_create]` - Spawns NuttX tasks via `task_create()`
- `[ws_terminal.c:posix_spawn]` - Spawns child processes via `posix_spawn()`

## Verification
- Run: `make test`
