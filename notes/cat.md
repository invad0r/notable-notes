---
tags: [coreutils, macos]
title: cat
created: '2019-09-04T06:20:06.676Z'
modified: '2021-02-23T08:23:29.609Z'
---

# cat

> concatenate and print files

## usage
```sh
cat > FILE          # then start typing and SIGINT to save

cat -e FILE         # display non printin characters

cat -s FILE         # Squeeze multiple adjacent empty lines, causing the output to be single spaced

# cat heredoc to file
cat <<EOF > FILE    
some random text
EOF

cat > FILE <<EOF
..
EOF
```

## see also
- [[heredoc]]
- [[signal]]
- [plan9 source code](https://9p.io/sources/plan9/sys/src/cmd/cat.c)
- [linux source code](https://git.savannah.gnu.org/cgit/coreutils.git/plain/src/cat.c)
- [[kubectl]]
