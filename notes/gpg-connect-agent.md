---
tags: [linux]
title: gpg-connect-agent
created: '2019-08-28T21:55:26.962Z'
modified: '2023-07-25T06:44:57.433Z'
---

# gpg-connect-agent

> connect to a running agent and send commands, runs via `pinentry` interactively or by passing options

## usage

```sh
gpg-connect-agent reloadagent /bye      # reload agent on macos to reenter passphrase for gpg

gpg-connect-agent 'getinfo std_env_names' /bye | awk '$1=="D" {print $2}' # list var name passed from gpg
```

## see also

- [[gpg]]
- [[pass]]
- [services - How can I restart gpg-agent? - Super User](https://superuser.com/a/1183544/341187)
