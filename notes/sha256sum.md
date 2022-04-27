---
tags: [linux]
title: sha256sum
created: '2019-11-26T06:51:16.688Z'
modified: '2022-03-31T08:08:03.347Z'
---

# sha256sum

> compute and check sha256 message digest

## flags

```sh
-b, --binary            # read in binary mode
-c, --check             # read checksums from the FILEs and check them
    --tag               # create a BSD-style checksum
-t, --text              # read in text mode (default)
-z, --zero              # end each output line with NUL, not newline, and disable file name escaping

    --ignore-missing    # don't fail or report status for missing files
    --quiet             # don't print OK for each successfully verified file
    --status            # don't output anything, status code shows success
    --strict            # exit non-zero for improperly formatted checksum lines
-w, --warn              # warn about improperly formatted checksum lines

    --help              # display this help and exit
    --version           # output version information and exit
```

## usage

```sh
sha256sum -c FILE FILE_linux_amd64.zip 2>&1 | grep OK    # reads checksums from FILE and checks them
```

## see also

- [[openssl]]
- [[md5sum]]
- [[gpg]]
