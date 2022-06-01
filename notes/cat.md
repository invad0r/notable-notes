---
tags: [coreutils, macos]
title: cat
created: '2019-09-04T06:20:06.676Z'
modified: '2022-05-17T19:20:50.994Z'
---

# cat

> concatenate and print files

## flags

```sh
-e   # display non printin characters
-s   # Squeeze multiple adjacent empty lines, causing the output to be single spaced
```

## usage

```sh
cat > FILE          # then start typing and SIGINT to save

# cat heredoc to file
cat <<EOF > FILE    
some random text
EOF

cat > FILE <<EOF
..
EOF
```

## see also

- [[less]]
- [[bat]]
- [[mkfifo]]
- [[heredoc]]
- [[signal]]
- [plan9 source code](https://9p.io/sources/plan9/sys/src/cmd/cat.c)
- [linux source code](https://git.savannah.gnu.org/cgit/coreutils.git/plain/src/cat.c)
- [[kubectl]]
- [Useless Use of Cat Award](http://porkmail.org/era/unix/award.html)
