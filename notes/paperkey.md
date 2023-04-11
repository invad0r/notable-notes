---
tags: [linux, macos]
title: paperkey
created: '2021-06-14T13:30:55.412Z'
modified: '2023-03-24T08:22:22.393Z'
---

# paperkey

> backup/extract only secret information out of OpenPGP secret keys

## install

```sh
brew install paperkey
```

## option

```sh
-o, --output-type TYPE    # TYPES
                          # "base16" is human readable
                          # "raw"    is useful if you want to pass the output to another program like a bar code or QR code generator

--input-type              # same as --output-type, but for the restore side of things. By default the input type is inferred automatically from the input data

--output-width            # sets the width of base16 output (i.e. given your font, how many columns fit on the paper you're printing on). Defaults to 78

--ignore-crc-error        # allows paperkey to continue when reconstructing even if it detects data corruption in the input

-v, --verbose             # be chatty about what is happening. Repeat this multiple times for more verbosity

-V, --version

--comment                 # add comment to base64 output
```

## usage

```sh
# take secret key in KEY.gpg and generate a file OUTPUT.txt that contains the secret data
paperkey \
  --secret-key KEY.gpg \
  --output OUTPUT.txt

# Take secret key data in my-key-text-file.txt and combine it with my-public-key.gpg to reconstruct my-secret-key.gpg
paperkey \
  --pubring my-public-key.gpg \
  --secrets my-key-text-file.txt \
  --output my-secret-key.gpg

gpg --export-secret-key KEY_ID | paperkey | lpr     # if --output is not specified output goes to STDOUT
                                                    # if --secret-key is not specified, the data is read from STDIN
```

## see also

- [jabberwocky.com/software/paperkey](https://www.jabberwocky.com/software/paperkey/)
- [[gpg]]
- [[lpr]]
