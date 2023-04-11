---
tags: [editor]
title: code
created: '2020-08-26T06:37:28.787Z'
modified: '2022-10-25T14:43:23.840Z'
---

# code

> cli bash-wrapper staring visual studio code

## option

```sh
-h --help                               # print usage
-d, --diff FILE FILE                    # diff files
-a, --add DIR                           # add to last active window
-g, --goto <file:line[:character]>      # open file at path on specified line and char pos
-n, --new-window                        # force open new window
-r, --reuse-window                      # force open file or dir in opened window
-w --wait                               # wait for the files to be closed before returning
--locale LOCALE                         # locale to use e.g. en-US, zh-TW
--user-data-dir DIR                     # specifies the directory that user data is kept in. Can be used to open multiple distinct instances of Code

--extensions-dir DIR                    # Set the root path for extensions
--list-extensions                       # List the installed extensions
--show-versions                         # Show versions of installed extensions, when using --list-extension
--category                              # Filters installed extensions by provided category, when using --list-extension
--install-extension EXTENSION           # installs or updates extension
--uninstall-extension ID                # uninstalls an extension
--enable-proposed-api ID                # enables proposed API features for extensions

-v --version                            # Print version
--verbose                               # Print verbose output (implies --wait)
--log LEVEL                             # log levels: 'critical', 'error', 'warn', 'info', 'debug', 'trace', 'off'
-s --status                             # print process usage and diagnostics information
--prof-startup                          # Run CPU profiler during startup
--disable-extensions                    # disable all installed extensions
--disable-extension EXT_ID              # disable an extension
--sync [on|off]                         # turn sync on or off
--inspect-extensions PORT               # allow debugging and profiling of extensions. connection URI via developer tools

--disable-gpu                           # disable GPU hardware acceleration
--max-memory                            # Max memory size for a window (in Mbytes)
--telemetry                             # Shows all telemetry events which VS code collects
```

## usage

```sh
code DIR

ps aux | grep code | code -             # read from stdin

code --list-extensions --show-versions | column -t -s@
```

## command palette

```sh
⌘ + ⇧ + p     # open command palette

workbench.action.reloadWindow   # usefull to restart lang server etc
```

## see also

- [[vim]]
- [[idea]]
- [[atom]]
- [[macos keyboard shortcuts]]
