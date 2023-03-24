---
tags: [linux, regex]
title: find
created: '2019-07-30T06:19:49.054Z'
modified: '2023-03-22T08:46:06.920Z'
---

# find

> walk a file hierarchy

## flags

```sh
-type
-exec
```

## usage

```sh
find . \( -name '*.txt' -o -name '*.md' \) \! -empty                        # .txt or .md files under the current directory that are not empty (> 0 bytes).

find . -iname '*expenses*'                                                  # case insensitive way to search for filenames

find . -exec CMD {} \;                                                      # escape semicolon to prevent shell from interpreting it

find . -exec CMD {} +                                                       # each result is appended to CMD and executed afterwards

find . -type f -exec chmod 664 '{}' \;

find . -type d -exec chmod ug=rwx,g+s,o=rx '{}' \;

find . -type f -exec sh -c 'for f; do echo "$f"; done' _ {} +               # argument _ is $0 in the shell; file-names are passed as the positional arguments

find . -type f -exec sh -c 'echo "$0"' {} \;                                # executes a separate shell for each file, which is equivalent but slightly slower

find . -exec echo {} \; -exec grep banana {} \;                             # the second -exec will only run if the first one returns successfully

find . \( -exec echo {} \; -o -exec true \; \) -exec grep banana {} \;      # both CMDs to run regardless of their success or failure


find . -type d -maxdepth 1 -exec bash -c 'pushd $(pwd) >/dev/null; cd {}; git remote get-url origin; popd >/dev/null;' \;



# patterns / regex .. `-name` uses pattern
find . -type f -name "[!.]*"    # ignore all dotfiles

find . -type f -name "*.txt"    # only .txt files

#`-regex`
find ...

# -mtime
find . -mtime +0    # find files modified greater than 24 hours ago
find . -mtime 0     # find files modified between now and 1 day ago
find . -mtime -1    # find files modified less than 1 day ago (SAME AS -mtime 0)
find . -mtime 1     # find files modified between 24 and 48 hours ago
find . -mtime +1    # find files modified more than 48 hours ago
```

## see also

- [unix.stackexchange.com/manipulate-file-name-piped-from-find-command](https://unix.stackexchange.com/a/60470/193945)
- [Exclude hidden files when searching with Unix/Linux find? - Super User](https://superuser.com/a/999448)
- [stackoverflow.com/find-exec-with-multiple-commands](https://stackoverflow.com/questions/5119946/find-exec-with-multiple-commands)
- [Why does find -exec mv {} ./target/ + not work? - Stack Overflow](https://stackoverflow.com/a/5607677)
