---
tags: [linux, systemd]
title: localectl
created: '2020-09-09T11:25:04.734Z'
modified: '2023-03-23T10:18:13.879Z'
---

# localectl

> control the system locale and keyboard layout settings

## usage
```sh
localectl list-locales

localectlstatus    # show current settings of the system locale and keyboard mapping.  If no command is specified, this is the implied default.

localectl set-locale LOCALE
localectl set-locale VARIABLE=LOCALE # set the system locale. This takes one locale such as"en_US.UTF-8", or takes one or more locale assignments such as "LANG=de_DE.utf8", "LC_MESSAGES=en_GB.utf8", and so on. If one locale without variable name is provided, then "LANG=" locale variable will be set. See locale(7) for details on the available settings and their meanings. Use list-locales for a list of available locales (see below).

localectl list-locales    # list available locales useful for configuration with set-locale.

localectl set-keymap MAP [TOGGLEMAP]

localectl list-keymaps  #  List available keyboard mappings for the console, useful for configuration with set-keymap.
```

## see also
- [[locale]]
