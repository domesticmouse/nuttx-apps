# `netutils`

## Overview
Groups Network Utilities (`netutils`) components and utilities for NuttX.

## Subdirectories & Boundaries
- `chat`: [./chat/README.md](./chat/README.md) - Provides Chat tool (`netutils/chat`). Enable the chat tool.
- `cmux`: [./cmux/README.md](./cmux/README.md) - Provides Cmux tool (`netutils/cmux`). Enable the CMUX (GSM 07.10) multiplexing protocol utility. CMUX allows multiplexing multiple virtual serial connections
- `codecs`: [./codecs/README.md](./codecs/README.md) - Provides CODEC Library (`netutils/codecs`). Enables the netutils/code library: Base64 coding, URL coding, MD5.
- `dhcp6c`: [./dhcp6c/README.md](./dhcp6c/README.md) - Implements DHCPv6 client (`netutils/dhcp6c`) for the NuttX application subsystem.
- `dhcpc`: [./dhcpc/README.md](./dhcpc/README.md) - Provides DHCP client (`netutils/dhcpc`). Enable support for the DHCP client.
- `dhcpd`: [./dhcpd/README.md](./dhcpd/README.md) - Provides DHCP server (`netutils/dhcpd`). Enable support for the DHCP server.
- `discover`: [./discover/README.md](./discover/README.md) - Provides Network Discovery Utility (`netutils/discover`). Tool for discovering devices on the local network per UDP broadcast.
- `dropbear`: [./dropbear/README.md](./dropbear/README.md) - Provides Dropbear SSH server (`netutils/dropbear`). Enable a minimal Dropbear SSH server port for NuttX. This initial port is based on the ESP-IDF MCU test port and provides a single
- `esp8266`: [./esp8266/README.md](./esp8266/README.md) - Provides ESP8266 (`netutils/esp8266`). Enable support for ESP8266 application interface.
- `ftpc`: [./ftpc/README.md](./ftpc/README.md) - Provides FTP client (`netutils/ftpc`). Enable support for the FTP client.
- `ftpd`: [./ftpd/README.md](./ftpd/README.md) - Provides FTP server (`netutils/ftpd`). Enable support for the FTP server.
- `iperf`: [./iperf/README.md](./iperf/README.md) - Provides iperf example (`netutils/iperf`). Enable the \"iperf example\"
- `iptables`: [./iptables/README.md](./iptables/README.md) - Provides iptables libary (`netutils/iptables`). iptable libary support.
- `libcoap`: [./libcoap/README.md](./libcoap/README.md) - Provides LIBCOAP (`netutils/libcoap`). libcoap is a C implementation of a lightweight application-protocol for devices that are constrained their resources such as computing
- `libcurl4nx`: [./libcurl4nx/README.md](./libcurl4nx/README.md) - Provides cURL4nx HTTP client library (`netutils/libcurl4nx`). Enable the NuttX cURL like library.
- `libwebsockets`: [./libwebsockets/README.md](./libwebsockets/README.md) - Provides libwebsockets library (current version) (`netutils/libwebsockets`). Enables the libwebsockets library.
- `mdns`: [./mdns/README.md](./mdns/README.md) - Provides MDNS library (`netutils/mdns`). Enable the mDNS library. This allows calls to the library to be made. This external library is "unlicensed" using the methodology from
- `netcat`: [./netcat/README.md](./netcat/README.md) - Provides NetCat tool (`netutils/netcat`). Enable the NetCat TCP/IP swiss army tool
- `netinit`: [./netinit/README.md](./netinit/README.md) - Provides Network initialization (`netutils/netinit`). This option enables/disables all support for common network initialization.
- `netlib`: [./netlib/README.md](./netlib/README.md) - Provides Network support library (`netutils/netlib`). Enable support for the network support library.
- `ntpclient`: [./ntpclient/README.md](./ntpclient/README.md) - Provides NTP client (`netutils/ntpclient`). Enable support for the minimal NTP client.
- `ping`: [./ping/README.md](./ping/README.md) - Provides ICMP ping support (`netutils/ping`). Build in support for a IPv4 ping command. This command ping will send the ICMP ECHO_REQUEST and wait for the ICMP ECHO_RESPONSE from
- `plcatool`: [./plcatool/README.md](./plcatool/README.md) - Provides plcatool support (`netutils/plcatool`). Build in support for the plcatool command. This command allows configuring the PLCA access method in 10BASE-T1S network adapters supporting PLCA.
- `pppd`: [./pppd/README.md](./pppd/README.md) - Provides PPP server (`netutils/pppd`). Enable support for the PPP daemon.
- `ptpd`: [./ptpd/README.md](./ptpd/README.md) - Provides PTPD client/server (`netutils/ptpd`). Build a minimal implementation of IEEE-1588 precision time protocol. Uses system gettimeofday() and adjtime() calls to synchronize clock
- `rexec`: [./rexec/README.md](./rexec/README.md) - Provides Remote execution client (`netutils/rexec`). Enable support for the remote execution client. Warning: rexec transmits passwords in cleartext, unencrypted.
- `rexecd`: [./rexecd/README.md](./rexecd/README.md) - Provides Remote Execution Server (`netutils/rexecd`). Enable support for the Remote Execution server. Warning: rexec transmits passwords in cleartext, unencrypted.
- `rtptools`: [./rtptools/README.md](./rtptools/README.md) - Provides Enable RTP Tools (`netutils/rtptools`). RTP Tools is a set of small applications that can be used for processing RTP data.
- `s2opc`: [./s2opc/README.md](./s2opc/README.md) - Provides S2OPC OPC UA toolkit (`netutils/s2opc`). Enable the S2OPC OPC UA client/server and UDP PubSub toolkit. The selected S2OPC release is downloaded when the applications tree is
- `smtp`: [./smtp/README.md](./smtp/README.md) - Provides SMTP (`netutils/smtp`). Enable support for SMTP.
- `telnetc`: [./telnetc/README.md](./telnetc/README.md) - Provides Telnet client library (`netutils/telnetc`). Enable support for the libtelnet. This is a public domain Telnet client library available from https://github.com/seanmiddleditch/libtelnet
- `telnetd`: [./telnetd/README.md](./telnetd/README.md) - Provides Telnet daemon (`netutils/telnetd`). Enable support for the Telnet daemon.
- `tftpc`: [./tftpc/README.md](./tftpc/README.md) - Provides TFTP client (`netutils/tftpc`). Enable support for the TFTP client.
- `thttpd`: [./thttpd/README.md](./thttpd/README.md) - Provides THTTPD webserver (`netutils/thttpd`). Enable support for the THTTPD webservert.
- `wakeonlan`: [./wakeonlan/README.md](./wakeonlan/README.md) - Provides WakeOnLAN support (`netutils/wakeonlan`). Enable the wake on LAN command "wol". This command sends a WakeOnLAN magic packet to target MAC address.
- `webclient`: [./webclient/README.md](./webclient/README.md) - Provides uIP web client (`netutils/webclient`). Enable support for the uIP web client.
- `webserver`: [./webserver/README.md](./webserver/README.md) - Provides uIP web server (`netutils/webserver`). Enable support for the uIP web server. This tiny web server was from uIP 1.0, but has undergone many changes. It is, however,
- `wifibridge`: [./wifibridge/README.md](./wifibridge/README.md) - Provides Wi-Fi SoftAP to Ethernet bridge (`netutils/wifibridge`). Library that turns a Wi-Fi interface into a SoftAP and bridges it to an Ethernet interface at layer 2, so that Ethernet devices
- `xmlrpc`: [./xmlrpc/README.md](./xmlrpc/README.md) - Provides XML RPC library (`netutils/xmlrpc`). Enables the Embeddable Lightweight XML-RPC Server discussed at http://www.drdobbs.com/web-development/an-embeddable-lightweight-xml-rpc-server/184405364
