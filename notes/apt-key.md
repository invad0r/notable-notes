---
tags: [linux]
title: apt-key
created: '2022-02-02T08:54:23.749Z'
modified: '2023-07-19T11:17:06.469Z'
---

# apt-key

> manage list of keys used by apt to authenticate packages

`apt-key` supports only the binary `openPGP` format (`"GPG key public ring"`) in files with the [[gpg]] extension

## option

```sh
-v, --version             # get version
-h, --help                # get help
    --keyring FILE        #
```

## usage

```sh
apt-key add FILE          # add a new key to the list of trusted keys

apt-key del KEY_ID        # Remove a key from the list of trusted keys

apt-key export KEY_ID     # output the key keyid to standard output

apt-key exportall         # output all trusted keys to standard output

apt-key list, finger      # list trusted keys with fingerprints

apt-key adv               # pass advanced options to gpg, with adv 

apt-key adv \
  --keyserver keyserver.ubuntu.com \
  --recv-keys KEY_ID      # --recv-key: download key from keyservers directly into the trusted set of keys
```

## see also

- [[gpg]]
- [[apt]]
- [[apt-get]]
- [[add-apt-repository]]
