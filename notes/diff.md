---
tags: [linux]
title: diff
created: '2019-07-30T06:19:49.036Z'
modified: '2021-06-04T12:24:42.958Z'
---

# diff

> compare files line by line

## usage
```sh
-q, --brief                       # output only whether files differ
-i, --ignore-case                 # ignore case differences in file contents
-y, --side-by-side                # output in two columns
-W NUM, --width=NUM               # output at most NUM (default 130) print columns
```
```sh
diff -q FILE1 FILE2                    # only output if files differ

diff -y FILE1 FILE2                    # side-by-side

diff --suppress-common-lines -y -W $(tput cols) FILE1 FILE2    # dynamic width, side-by-side

diff -y -W $(tput cols) <(CMD | jq -S) <(CMD | jq -S)

diff --unified FILE1 FILE2

diff <(sort <(md5deep -r /$1/) |cut -f1 -d' ') <(sort <(md5deep -r /$2/) |cut -f1 -d' ')

diff -y <(curl -s URL) <(cat $(brew --prefix)/PATH/git-completion.bash)

```

## see also
- [[bash process substitution]]
- [[tput]]
- [[column]]
- [Make diff Use Full Terminal Width in Side-by-Side Mode - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/9303)
- [[colordiff]]
