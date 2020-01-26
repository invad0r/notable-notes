---
tags: [linux]
title: mktemp
created: '2019-11-26T08:13:04.385Z'
modified: '2020-01-23T08:24:56.081Z'
---

# mktemp

> create a temporary file or directory, safely, and print its name

## usage
```sh
mktemp -d                   # make a directory instead of a file

mkdtemp -t $(basename $0)  # generate a template (using the supplied prefix and TMPDIR if set) to create a filename template.


trap 'rm -rf "${WORKSPACE}"' EXIT
WORKSPACE="$(mktemp --directory)"
```

## see also
- [[bash trap]]
- [[bash pushd popd]]
