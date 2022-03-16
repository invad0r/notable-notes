---
title: apt-key
created: '2022-02-02T08:54:23.749Z'
modified: '2022-02-02T09:05:25.527Z'
---

# apt-key

> used to manage the list of keys used by apt to authenticate packages

apt-key supports only the binary `OpenPGP` format (aka "GPG key public ring") in files with the [[gpg]] extension

## flags

```sh
-v, --version             # get version
-h, --help                # get help
    --keyring FILE        #
```

## commands

```sh
add FILE          # add a new key to the list of trusted keys

del KEY_ID        # Remove a key from the list of trusted keys

export KEY_ID     # output the key keyid to standard output

exportall         # output all trusted keys to standard output

list, finger      # list trusted keys with fingerprints

adv               # pass advanced options to gpg, with adv --recv-key you can download key from keyservers directly into the trusted set of keys
```

## usage

```sh
apt-key adv --keyserver keyserver.ubuntu.com --recv-keys KEY_ID
```

## see also

- [[gpg]]
- [[apt]]
- [[apt-get]]
- [[add-apt-repository]]
