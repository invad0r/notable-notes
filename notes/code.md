---
tags: [editor]
title: code
created: '2020-08-26T06:37:28.787Z'
modified: '2021-06-07T07:05:32.312Z'
---

# code

> cli bash-wrapper staring visual studio code

## usage
```sh
-h --help                               # print usage
-d, --diff FILE FILE                    # diff files
-a, --add DIR                           # add to last active window
-g, --goto <file:line[:character]>      # open file at path on specified line and char pos
-n, --new-window                        # force open new window
-r, --reuse-window                      # force open file or dir in opened window
-w --wait                               # wait for the files to be closed before returning
--locale <locale>                       # locale to use (e.g. en-US or zh-TW).
--user-data-dir <dir>                   # specifies the directory that user data is kept in. Can be used to open multiple distinct instances of Code.

--extensions-dir <dir>                  # Set the root path for extensions.
--list-extensions                       # List the installed extensions.
--show-versions                         # Show versions of installed extensions, when using --list-extension.
--category                              # Filters installed extensions by provided category, when using --list-extension.
--install-extension EXTENSION           # installs or updates extension
--uninstall-extension ID                # uninstalls an extension.
--enable-proposed-api ID                # enables proposed API features for extensions

-v --version                            # Print version.
--verbose                               # Print verbose output (implies --wait).
--log LEVEL                             # log levels: 'critical', 'error', 'warn', 'info', 'debug', 'trace', 'off'
-s --status                             # print process usage and diagnostics information.
--prof-startup                          # Run CPU profiler during startup
--disable-extensions                    # Disable all installed extensions.
--disable-extension <extension-id>      # Disable an extension.
--sync <on> <off>                       # Turn sync on or off
--inspect-extensions <port>             # Allow debugging and profiling of extensions. Check the developer tools for the connection URI.

--disable-gpu                           # Disable GPU hardware acceleration.
--max-memory                            # Max memory size for a window (in Mbytes).
--telemetry                             # Shows all telemetry events which VS code collects.
```

```sh
code DIR

ps aux | grep code | code -             # read from stdin
```

## see also
- [[idea]]
- [[atom]]
