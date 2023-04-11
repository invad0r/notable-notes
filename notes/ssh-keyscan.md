---
tags: [crypto, linux]
title: ssh-keyscan
created: '2021-06-30T12:48:52.502Z'
modified: '2023-03-25T12:05:18.593Z'
---

# ssh-keyscan

> gather ssh host public keys from servers

## option

```sh
-4            # Force ssh-keyscan to use IPv4 addresses only
-6            # Force ssh-keyscan to use IPv6 addresses only
-c            # Request certificates from target hosts instead of plain keys
-D            # Print keys found as SSHFP DNS records. The default is to print keys in a format usable as a `ssh` known_hosts file
-f FILE       # Read hosts or “addrlist namelist” pairs from file, one per line
              # If ‘-’ is supplied instead of a filename, ssh-keyscan will read from the standard input
              # Input is expected in the format: 1.2.3.4,1.2.4.4 name.my.domain,name,n.my.domain,n,1.2.3.4,1.2.4.4
-H            # hash all hostnames and addresses in the output
              # Hashed names may be used normally by `ssh` and `sshd`, but they do not reveal identifying information should the file's contents be disclosed
-p PORT       # connect to port on the remote host
-T timeout    # set the timeout for connection attempts - default: 5 sec
-t type       # type of key to fetch from the scanned hosts - values: dsa, ecdsa, ed25519, rsa. Multiple values may be specified by separating them with commas
              # default is to fetch “rsa”, “ecdsa”, and “ed25519” keys
-v            # print debugging messages about progress
```

## usage

```sh
ssh-keyscan -H github.com >> ~/.ssh/known_hosts

ssh-keyscan -H IP >> ~/.ssh/known_hosts

ssh-keyscan -t rsa,dsa HOST 2>&1 | sort -u - ~/.ssh/known_hosts 
```

## see also

- [[ssh]]
- [[git]]
