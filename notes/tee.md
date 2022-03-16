---
tags: [coreutils]
title: tee
created: '2019-07-30T06:19:49.251Z'
modified: '2022-02-01T15:14:56.131Z'
---

# tee

> `tee` "pipe fitting" - copy stdin to stdout and move stdin further

## usage

```sh
-a      # append output to files rather than overwriting
-i      # ignore the SIGINT
```

```sh
CMD | tee file.log   # print to stdout and to file

# redirecting from tee to multiple files
CMD | tee >(jq -r .data > data.json) >(jq -r .id > id.json) >(jq -r .user > user.json)


echo 'IP HOST' | sudo tee -a /etc/hosts     # append with sudo
```

## see also

- [[pee]]
- [[jq]]
- [[sponge]]
- [[bash redirects]]
- [[bash process substitution]]
