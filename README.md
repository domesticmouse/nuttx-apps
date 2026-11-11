# Application Folder

## Contents

- General
- Directory Location
- Built-In Applications
- NuttShell (NSH) Built-In Commands
- Synchronous Built-In Commands
- Application Configuration File
- Example Built-In Application
- Building NuttX with Board-Specific Pieces Outside the Source Tree

## General

This folder provides various applications found in sub-directories. These
applications are not inherently a part of NuttX but are provided to help you
develop your own applications. The `apps/` directory is a _break away_ part of
the configuration that you may choose to use or not.

## Directory Location

The default application directory used by the NuttX build should be named
`apps/` (or `apps-x.y.z/` where `x.y.z` is the NuttX version number). This
`apps/` directory should appear in the directory tree at the same level as the
NuttX directory. Like:

```
 .
 |- nuttx
 |
 `- apps
```

If all of the above conditions are TRUE, then NuttX will be able to find the
application directory. If your application directory has a different name or is
located at a different position, then you will have to inform the NuttX build
system of that location. There are several ways to do that:

1) You can define `CONFIG_APPS_DIR` to be the full path to your application
   directory in the NuttX configuration file.
2) You can provide the path to the application directory on the command line
   like: `make APPDIR=<path>` or `make CONFIG_APPS_DIR=<path>`
3) When you configure NuttX using `tools/configure.sh`, you can provide that
   path to the application directory on the configuration command line like:
   `./configure.sh -a <app-dir> <board-name>:<config-name>`

## Built-In Applications

NuttX also supports applications that can be started using a name string. In
this case, application entry points with their requirements are gathered
together in two files:

- `builtin/builtin_proto.h` – Entry points, prototype function
- `builtin/builtin_list.h` – Application specific information and requirements

The build occurs in several phases as different build targets are executed: (1)
context, (2) depend, and (3) default (all). Application information is collected
during the make context build phase.

To execute an application function:

`exec_builtin()` is defined in the `apps/include/builtin/builtin.h`.

## NuttShell (NSH) Built-In Commands

One use of builtin applications is to provide a way of invoking your custom
application through the NuttShell (NSH) command line. NSH will support a
seamless method invoking the applications, when the following option is enabled
in the NuttX configuration file:

```conf
CONFIG_NSH_BUILTIN_APPS=y
```

Applications registered in the `apps/builtin/builtin_list.h` file will then be
accessible from the NSH command line. If you type `help` at the NSH prompt, you
will see a list of the registered commands.

## Synchronous Built-In Commands

By default, built-in commands started from the NSH command line will run
asynchronously with NSH. If you want to force NSH to execute commands then wait
for the command to execute, you can enable that feature by adding the following
to the NuttX configuration file:

```conf
CONFIG_SCHED_WAITPID=y
```

The configuration option enables support for the `waitpid()` RTOS interface.
When that interface is enabled, NSH will use it to wait, sleeping until the
built-in command executes to completion.

Of course, even with `CONFIG_SCHED_WAITPID=y` defined, specific commands can
still be forced to run asynchronously by adding the ampersand (`&`) after the
NSH command.

## Application Configuration File

The NuttX configuration uses `kconfig-frontends` tools and the NuttX
configuration file (`.config`) file. For example, the NuttX `.config` may have:

```conf
CONFIG_EXAMPLES_HELLO=y
```

This will select the `apps/examples/hello` in the following way:

- The top-level make will include `apps/examples/Make.defs`
- `apps/examples/Make.defs` will set `CONFIGURED_APPS += $(APPDIR)/examples/hello`
  like this:

```makefile
  ifneq ($(CONFIG_EXAMPLES_HELLO),)
  CONFIGURED_APPS += $(APPDIR)/examples/hello
  endif
```

## Example Built-In Application

An example application skeleton can be found under the `examples/hello`
sub-directory. This example shows how a builtin application can be added to the
project. One must:

 1. Create sub-directory as: progname

 2. In this directory there should be:

    - A `Make.defs` file that would be included by the `apps/Makefile`
    - A `Kconfig` file that would be used by the configuration tool (see the
      file `kconfig-language.txt` in the NuttX tools repository). This `Kconfig`
      file should be included by the `apps/Kconfig` file
    - A `Makefile`, and
    - The application source code.

 3. The application source code should provide the entry point:

    ```c
    main()
    ```

 4. Set the requirements in the file: `Makefile`, specifically the lines:

    ```makefile
    PROGNAME   = progname
    PRIORITY   = SCHED_PRIORITY_DEFAULT
    STACKSIZE  = 768
    ASRCS      = asm source file list as a.asm b.asm ...
    CSRCS      = C source file list as foo1.c foo2.c ..
    ```

 5. The `Make.defs` file should include a line like:

    ```makefile
    ifneq ($(CONFIG_PROGNAME),)
    CONFIGURED_APPS += progname
    endif
    ```

## Building NuttX with Board-Specific Pieces Outside the Source Tree

Q: Has anyone come up with a tidy way to build NuttX with board- specific pieces
   outside the source tree?

A: Here are three:

   1) There is a make target called `make export`. It will build NuttX, then
      bundle all of the header files, libraries, startup objects, and other
      build components into a `.zip` file. You can move that `.zip` file into
      any build environment you want. You can even build NuttX under a DOS `CMD`
      window.

      This make target is documented in the top level `nuttx/README.txt`.

   2) You can replace the entire `apps/` directory. If there is nothing in the
      `apps/` directory that you need, you can define `CONFIG_APPS_DIR` in your
      `.config` file so that it points to a different, custom application
      directory.

      You can copy any pieces that you like from the old apps/directory to your
      custom apps directory as necessary.

      This is documented in `NuttX/boards/README.txt` and `NuttX Porting Guide`
      online at <https://cwiki.apache.org/confluence/display/NUTTX/Porting+Guide>.

   3) If you like the random collection of stuff in the `apps/` directory but
      just want to expand the existing components with your own, external
      sub-directory then there is an easy way to that too: You just create a
      symbolic link in the `apps/` directory that redirects to your application
      sub-directory.

      In order to be incorporated into the build, the directory that you link
      under the `apps/` directory should contain (1) a `Makefile` that supports
      the `clean` and `distclean` targets (see other `Makefile`s for examples),
      and (2) a tiny `Make.defs` file that simply adds the custom build
      directories to the variable `CONFIGURED_APPS` like:

      ```makefile
      CONFIGURED_APPS += my_directory1 my_directory2
      ```

      The `apps/Makefile` will always automatically check for the existence of
      subdirectories containing a `Makefile` and a `Make.defs` file. The
      `Makefile` will be used only to support cleaning operations. The Make.defs
      file provides the set of directories to be built; these directories must
      also contain a `Makefile`. That `Makefile` must be able to build the
      sources and add the objects to the `apps/libapps.a` archive. (see other
      `Makefile`s for examples). It should support the all, install, context,
      and depend targets.

      `apps/Makefile` does not depend on any hardcoded lists of directories.
      Instead, it does a wildcard search to find all appropriate directories.
      This means that to install a new application, you simply have to copy the
      directory (or link it) into the `apps/` directory. If the new directory
      includes a `Makefile` and `Make.defs` file, then it will automatically be
      included in the build.

      If the directory that you add also includes a `Kconfig` file, then it will
      automatically be included in the NuttX configuration system as well.
      `apps/Makefile` uses a tool at `apps/tools/mkkconfig.sh` that dynamically
      builds the `apps/Kconfig` file at pre-configuration time.

      You could, for example, create a script called `install.sh` that installs
      a custom application, configuration, and board specific directory:

      a) Copy `MyBoard` directory to `boards/MyBoard`.
      b) Add a symbolic link to `MyApplication` at `apps/external`.
      c) Configure NuttX, usually by:

      ```bash
      tools/configure.sh MyBoard:MyConfiguration
      ```

      Use of the name `apps/external` is suggested because that name is included
      in the `.gitignore` file and will save you some nuisance when working with
      GIT.

# Export restrictions

This distribution includes cryptographic software. The country in which you
currently reside may have restrictions on the import, possession, use, and/or
re-export to another country, of encryption software. BEFORE using any encryption
software, please check your country's laws, regulations and policies concerning
the import, possession, or use, and re-export of encryption software, to see if
this is permitted. See <http://www.wassenaar.org/> for more information.

The U.S. Government Department of Commerce, Bureau of Industry and Security (BIS),
has classified this software as Export Commodity Control Number (ECCN) 5D002.C.1,
which includes information security software using or performing cryptographic
functions with asymmetric algorithms. The form and manner of this Apache Software
Foundation distribution makes it eligible for export under the License Exception ENC
Technology Software Unrestricted (TSU) exception (see the BIS Export Administration
Regulations, Section 740.13) for both object code and source code.

The following provides more details on the included cryptographic software:
https://tls.mbed.org/supported-ssl-ciphersuites.
https://github.com/intel/tinycrypt

## Overview

The `apps` directory is the Apache NuttX user-space application repository. It provides built-in applications (`builtin`), the NuttShell (`nshlib`) command interpreter, system utilities (`system`), networking protocols and daemons (`netutils`), filesystem tools (`fsutils`), graphics and widget toolkits (`graphics`), industrial control stacks (`industry`), language interpreters and WebAssembly runtimes (`interpreters`), cryptographic libraries (`crypto`), audio/video utilities (`audioutils`, `videoutils`), wireless and LTE stacks (`wireless`, `lte`), machine learning and SDR libraries (`mlearning`, `sdr`), bootloaders (`boot`), benchmarks (`benchmarks`), and reference example applications (`examples`).

## Subdirectories & Boundaries

- `audioutils`: [./audioutils/README.md](./audioutils/README.md) - User-space audio playback helpers (`nxaudio`), Music Macro Language score parsers (`mml_parser`), and software Frequency Modulation synthesizer libraries (`fmsynth`).
- `benchmarks`: [./benchmarks/README.md](./benchmarks/README.md) - CPU, cache, memory, filesystem, flash, and RTOS latency benchmark applications (`cachespeed`, `cyclictest`, `mtd`, `osperf`, `ramspeed`, `rt-tests`, `sd_bench`, `spinlock_bench`, `tacle-bench`, `whetstone`).
- `boot`: [./boot/README.md](./boot/README.md) - Bootloader applications and firmware update utilities (`miniboot`, `nxboot`).
- `builtin`: [./builtin/README.md](./builtin/README.md) - Build-time `.bdat`/`.pdat` registry (`g_builtins`, `g_builtin_count`) and runtime execution engine (`exec_builtin()`) for NuttX built-in applications.
- `canutils`: [./canutils/README.md](./canutils/README.md) - SocketCAN and character-driver CAN utilities and libraries (`candump`, `canlib`, `cansend`, `libcanutils`, `libobd2`, `slcan`).
- `crypto`: [./crypto/README.md](./crypto/README.md) - Cryptographic libraries, TLS stacks, and hardware secure element tools (`controlse`, `mbedtls`, `openssl_mbedtls_wrapper`, `wolfssl`).
- `database`: [./database/README.md](./database/README.md) - Embedded database engines and CLI utilities (`sqlite`).
- `examples`: [./examples/README.md](./examples/README.md) - User-space reference example applications and demonstration suites for device drivers, networking protocols, filesystems, graphics, IPC, and language runtimes.
- `fsutils`: [./fsutils/README.md](./fsutils/README.md) - Filesystem formatting libraries (`mkfatfs`, `mksmartfs`, `mkgpt`, `mkmbr`), MTD flash utilities (`flash_eraseall`, `flashtool`), INI/IP configuration parsers (`inifile`, `ipcfg`), and password management (`passwd`).
- `games`: [./games/README.md](./games/README.md) - Embedded console, LED-matrix, and framebuffer games (`NXDoom`, `brickmatch`, `cgol`, `match4`, `snake`).
- `graphics`: [./graphics/README.md](./graphics/README.md) - Graphics libraries, window managers, widget toolkits, and display utilities (`ft80x`, `input`, `jpgresizetool`, `nxglyphs`, `nxwidgets`, `nxwm`, `pdcurs34`, `screenshot`, `slcd`, `tiff`, `twm4nx`).
- `include`: [./include/README.md](./include/README.md) - Shared public C/C++ header interfaces exported across application subsystems (`audioutils`, `builtin`, `canutils`, `fsutils`, `graphics`, `industry`, `interpreters`, `logging`, `lte`, `modbus`, `netutils`, `nshlib`, `nxmodbus`, `platform`, `system`, `wireless`).
- `industry`: [./industry/README.md](./industry/README.md) - Industrial control, motor control, and protocol stacks (`abnt_codi`, `cnc`, `foc`, `modbus`, `nxmodbus`).
- `interpreters`: [./interpreters/README.md](./interpreters/README.md) - Embedded scripting language interpreters and WebAssembly runtimes (`bas`, `berry`, `ficl`, `lua`, `minibasic`, `python`, `quickjs`, `toywasm`, `wamr`).
- `logging`: [./logging/README.md](./logging/README.md) - Real-time telemetry and multi-channel diagnostic logging libraries (`nxscope`).
- `lte`: [./lte/README.md](./lte/README.md) - LTE modem user-space socket daemons (`alt1250`) and LTE API client libraries (`lapi`).
- `mlearning`: [./mlearning/README.md](./mlearning/README.md) - Embedded machine learning inference frameworks (`tflite-micro`).
- `netutils`: [./netutils/README.md](./netutils/README.md) - User-space networking libraries, protocol daemons, and client utilities (`chat`, `cmux`, `codecs`, `dhcp6c`, `dhcpc`, `dhcpd`, `discover`, `dropbear`, `esp8266`, `ftpc`, `ftpd`, `iperf`, `iptables`, `libcoap`, `libcurl4nx`, `libwebsockets`, `mdns`, `netcat`, `netinit`, `netlib`, `ntpclient`, `ping`, `plcatool`, `pppd`, `ptpd`, `rexec`, `rexecd`, `rtptools`, `s2opc`, `smtp`, `telnetc`, `telnetd`, `tftpc`, `thttpd`, `wakeonlan`, `webclient`, `webserver`, `wifibridge`, `xmlrpc`).
- `nshlib`: [./nshlib/README.md](./nshlib/README.md) - Core NuttShell (NSH) command line parser, session manager, and built-in command dispatcher (`nsh_initialize`, `nsh_consolemain`, `nsh_telnetstart`, `nsh_system`, `nsh_session`, `nsh_parse`, `nsh_command`).
- `platform`: [./platform/README.md](./platform/README.md) - Build integration point for board-specific user-space platform code (`dummy`, `mikroe-stm32f4`).
- `sdr`: [./sdr/README.md](./sdr/README.md) - Software-defined radio DSP libraries (`liquid_dsp`).
- `system`: [./system/README.md](./system/README.md) - System libraries, device diagnostic utilities, and NSH add-on commands (`adb`, `adcscope`, `batterydump`, `brctl`, `cdcacm`, `cfgdata`, `cle`, `composite`, `conntrack`, `coredump`, `cpuload`, `critmon`, `cu`, `curl`, `dd`, `debugpoint`, `dhcp6c`, `dhcpc`, `dumpstack`, `expat`, `fastboot`, `flash_eraseall`, `gcov`, `gdbstub`, `gprof`, `grep`, `hex2bin`, `hexed`, `hostname`, `i2c`, `iptables`, `irtest`, `kbd`, `lm75`, `lsan`, `lzf`, `mdio`, `microros`, `netdb`, `nsh`, `ntpc`, `nxcamera`, `nxcodec`, `nxdiag`, `nxinit`, `nxlooper`, `nxmbclient`, `nxpkg`, `nxplayer`, `nxrecorder`, `nxstore`, `ofloader`, `ping`, `ping6`, `ptpd`, `readline`, `resmonitor`, `sched_note`, `sensorscope`, `sensortest`, `setlogmask`, `settings`, `smf`, `spi`, `stackmonitor`, `stty`, `sudo`, `syslogd`, `system`, `taskset`, `tcpdump`, `tee`, `telnet`, `telnetd`, `termcurses`, `toybox`, `trace`, `ubloxmodem`, `uniqueid`, `uorb`, `usbmsc`, `vi`, `vncviewer`, `wifibridge`, `xipfs`, `xrcedds`, `ymodem`, `zbus`, `zmodem`).
- `tools`: [./tools/README.md](./tools/README.md) - Host-side build scripts, symbol-table generators (`mksymtab.sh`), Kconfig aggregators (`mkkconfig.sh`), hash verifiers (`check-hash.sh`), ROMFS/import archive scripts (`mkromfsimg.sh`, `mkimport.sh`), and WASI-SDK WebAssembly build rules (`Wasm.mk`, `WASI-SDK.defs`).
- `videoutils`: [./videoutils/README.md](./videoutils/README.md) - Video encoding and decoding libraries (`openh264`).
- `wireless`: [./wireless/README.md](./wireless/README.md) - Wireless protocol stacks, Bluetooth tools, IEEE 802.15.4 utilities, LoRa packet forwarders, and Wi-Fi configuration utilities (`bluetooth`, `gs2200m`, `ieee802154`, `iwpan`, `lora_pkt_fwd`, `wapi`).

## Interface

- `[builtin/builtin_list.c:g_builtins]` Built-in application descriptor table (`const struct builtin_s g_builtins[]`) and `[builtin/builtin_list.c:g_builtin_count]` count exported to the kernel and NSH.
- `[builtin/exec_builtin.c:exec_builtin]` Launches a registered built-in application by name (`int exec_builtin(FAR const char *appname, FAR char * const *argv, FAR const struct spawn_syscall_parms_s *parm)`).
- `[nshlib/nsh_init.c:nsh_initialize]` Initializes the NuttShell environment, mounts configured filesystems, brings up networking, and runs startup scripts.
- `[nshlib/nsh_consolemain.c:nsh_consolemain]` Runs the interactive serial/console NSH session loop.
- `[Application.mk:PROGNAME]` Standard build rules for compiling, registering (`REGISTER`), and archiving user-space applications into `libapps.a`.
- `[Makefile:libapps.a]` Top-level application library archive (`BIN = libapps$(LIBEXT)`) linked against the NuttX kernel.

## Invariants

- Built-in applications registered via `Application.mk` (`PROGNAME`, `PRIORITY`, `STACKSIZE`, `MAIN`) populate `.bdat`/`.pdat` entries during the `context`/`register` build phase before `builtin_list.c` is compiled `[Application.mk:REGISTER]`.
- Subdirectories containing both `Makefile` and `Make.defs` are discovered dynamically by `[Directory.mk:SUBDIRS]` and `[Make.defs:CONFIGURED_APPS]` via `.config` Kconfig symbols.
- When `CONFIG_SCHED_WAITPID=y` is enabled, NSH waits synchronously for foreground built-in commands unless backgrounded with `&` `[nshlib/nsh_builtin.c:nsh_builtin]`.

## Side Effects

- Building `context` executes `[tools/mkkconfig.sh]` to generate `Kconfig` and populates `builtin/registry/` `.bdat`/`.pdat` metadata files.
- Compiling applications archives object files into `libapps.a` (`$(BIN)`) and installs loadable ELF/NXFLAT/Wasm binaries into `bin/` or ROMFS images (`romfs.img`, `boot_romfsimg.h`) when configured `[Application.mk:install]`.

## Verification

- Run: `make test`

