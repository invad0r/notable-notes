---
tags: [linux, osx]
title: cat
created: '2019-09-04T06:20:06.676Z'
modified: '2020-01-27T07:13:34.928Z'
---

# cat

> concatenate and print files

```sh
cat -e file       # display non printin characters

cat -s file       # Squeeze multiple adjacent empty lines, causing the output to be single spaced

cat <<EOF > file  # cat heredoc to file
..
EOF
```

## see also
- [[heredoc]]
- [plan9 source code](https://9p.io/sources/plan9/sys/src/cmd/cat.c)
- [linux source code](https://git.savannah.gnu.org/cgit/coreutils.git/plain/src/cat.c)
