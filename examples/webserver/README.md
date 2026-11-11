# webserver

## Overview
uIP web server example (`webserver`). Enable the uIP web server example

## Interface
- `[Kconfig:EXAMPLES_WEBSERVER]` - Build configuration option `EXAMPLES_WEBSERVER`
- `[Kconfig:EXAMPLES_WEBSERVER_IPADDR]` - Build configuration option `EXAMPLES_WEBSERVER_IPADDR`
- `[Makefile:PROGNAME]` - Registers application/module target `webserver`
- `[CMakeLists.txt:nuttx_add_application]` - Registers application/module target `webserver`
- `[cgi.h:cgi_register]` - Public function declaration `cgi_register()`
- `[webserver_main.c:main]` - Application entry point `main()`
- `[cgi.c:cgi_register]` - Public function `cgi_register()`

## Invariants
- `[webserver_main.c:#error]` - Compile-time precondition: CONFIG_NETUTILS_WEBSERVER is required to get WebServer working
- `[webserver_main.c:CONFIG_EXAMPLES_WEBSERVER_DHCPC]` - Configuration guard on `CONFIG_EXAMPLES_WEBSERVER_DHCPC`
- `[webserver_main.c:CONFIG_NETUTILS_WEBSERVER]` - Configuration guard on `CONFIG_NETUTILS_WEBSERVER`
- `[webserver_main.c:CONFIG_NSH_NETINIT]` - Configuration guard on `CONFIG_NSH_NETINIT`
- `[webserver_main.c:CONFIG_EXAMPLES_WEBSERVER_NOMAC]` - Configuration guard on `CONFIG_EXAMPLES_WEBSERVER_NOMAC`
- `[cgi.c:CONFIG_NETUTILS_HTTPDFILESTATS]` - Configuration guard on `CONFIG_NETUTILS_HTTPDFILESTATS`
- `[cgi.c:CONFIG_NETUTILS_HTTPDNETSTATS]` - Configuration guard on `CONFIG_NETUTILS_HTTPDNETSTATS`
- `[cgi.c:CONFIG_NETUTILS_HTTPD_ENABLE_CHUNKED_ENCODING]` - Configuration guard on `CONFIG_NETUTILS_HTTPD_ENABLE_CHUNKED_ENCODING`

## Side Effects
- `[webserver_main.c:printf]` - Writes formatted output to standard output via `printf()`

## Verification
- Run: `make test`
