---
tags: [linux]
title: diff
created: '2019-07-30T06:19:49.036Z'
modified: '2021-03-15T10:32:21.191Z'
---

# diff

> compare files line by line

## usage
```sh
diff -q file1 file2                    # only output if files differ

diff -y file1 file2                    # side-by-side

diff --suppress-common-lines -y -W $(tput cols) file1 file2    # dynamic width, side-by-side

diff --unified file1 file2

# options:
#   -q, --brief               output only whether files differ
#   -i, --ignore-case         ignore case differences in file contents
#   -y, --side-by-side        output in two columns
#   -W NUM, --width=NUM       output at most NUM (default 130) print columns

diff <(sort <(md5deep -r /$1/) |cut -f1 -d' ') <(sort <(md5deep -r /$2/) |cut -f1 -d' ')

diff -y <(curl -s https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.bash) \
  <(cat $(brew --prefix)/etc/bash_completion.d/git-completion.bash)
```

## see also
- [[bash process substitution]]
- [[tput]]
- [[column]]
- [Make diff Use Full Terminal Width in Side-by-Side Mode - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/9303)
- [[colordiff]]
