---
tags: [buildsystem, c]
title: autoconf
created: '2022-02-02T13:35:55.731Z'
modified: '2023-03-22T10:40:07.333Z'
---

# autoconf

> generate configuration scripts

## option

```sh
# operation modes
-h, --help                      # print this help, then exit
-V, --version                   # print version number, then exit
-v, --verbose                   # verbosely report processing
-d, --debug                     # don't remove temporary files
-f, --force                     # consider all files obsolete
-o, --output=FILE               # save output in FILE (stdout is the default)
-W, --warnings=CATEGORY         # report the warnings falling in CATEGORY

# library directories
-B, --prepend-include=DIR       # prepend directory DIR to search path
-I, --include=DIR               # append directory DIR to search path

# tracing
-t, --trace=MACRO[:FORMAT]      # report the list of calls to MACRO
-i, --initialization            # also trace autoconf's initialization process
```

## usage

```sh
autoreconf -fi    # generate config script
```

## see also

- [[make]]
- [[automake]]
- [[curl]]
