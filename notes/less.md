---
tags: [linux, macos]
title: less
created: '2022-05-17T19:16:57.688Z'
modified: '2023-05-19T11:25:17.456Z'
---

# less

> opposite of [[more]]

## env

```sh
COLUMNS       # setsnumber of columns on the screen
EDITOR        # name of the editor (used for the v command)
HOME          # Name of the user's home directory (used to find a lesskey file on Unix and OS/2 systems)
INIT          # Name of the user's init directory (used to find a lesskey file on OS/2 systems)
LANG          # Language for determining the character set.
LC_CTYPE      # Language for determining the character set.
LESS          # Options which are passed to less automatically.
LESSSECURE    # set to 1, less runs in a "secure" mode, disables features
LESS_IS_MORE  # set to 1, less behaves (mostly) in conformance with the POSIX "more" command specification
```

## option

```sh
-s, --squeeze-blank-lines   # causes consecutive blank lines to be squeezed into a single blank line
-r, --raw-control-chars     # causes "raw" control characters to be displayed
-R, --RAW-CONTROL-CHARS     # like -r, but only ANSI "color" escape sequences and OSC 8 hyperlink sequences are output in "raw" form
```

## usage

```sh
less FILE

less -sR    # see man, if color support is enabled
```

## see also

- [[ascii]]
- [[man]]
- [[cat]]
- [[vim]]
- [[more]]
- [[jless]]
