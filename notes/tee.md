---
tags: [coreutils]
title: tee
created: '2019-07-30T06:19:49.251Z'
modified: '2023-04-17T06:10:02.424Z'
---

# tee

> `tee` "pipe fitting" - copy stdin to stdout and move stdin further

## option

```sh
-a      # append output to files rather than overwriting
-i      # ignore the SIGINT
```

## usage

```sh
CMD | tee file.log            # print to STDOUT and to file

CMD | tee /dev/tty | wc -l    # print to STDOUT and pipe to next command

# redirecting from tee to multiple files
CMD | tee >(jq -r .data > data.json) >(jq -r .id > id.json) >(jq -r .user > user.json)


echo 'IP HOST' | sudo tee -a /etc/hosts     # append with sudo
```

## see also

- [[pee]]
- [[cat]]
- [[jq]]
- [[sponge]]
- [[bash redirects]]
- [[bash process substitution]]
