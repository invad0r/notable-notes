---
tags: [coreutils, macos]
title: ln
created: '2019-08-28T09:33:38.811Z'
modified: '2022-04-09T09:39:32.427Z'
---

# ln

> make links between files

## option

```sh
 -F     # if target file already exists and is a directory, then remove it so that the link may occur, should be used with either -f or -i options
        # if neither -f nor -i is specified, -f is implied. -F option is a no-op unless -s is specified

-L      # when creating a hard link to a symbolic link, create a hard link to the target of the symbolic link. This is the default. cancels the -P option

-P      # when creating a hard link to a symbolic link, create a hard link to the symbolic link itself. cancels the -L option

-f      # if the target file already exists, then unlink it so that the link may occur.  (The -f option overrides any previous -i and -w options.)

-h      # if the target_file or target_dir is a symbolic link, do not follow it.  This is most useful with the -f option, to replace a symlink which may point to a directory.

-i      # cause ln to write a prompt to standard error if the target file exists
        # if response from the stdin begins with the character ‘y’ or ‘Y’, then unlink the target file so that the link may occur

-s      # create a symbolic link

-v      # be verbose, showing files as they are processed

-w      # warn if the source of a symbolic link does not currently exist
```

## usage

```sh
ln -s SOURCE_FILENAME SYMBOLIC_FILENAME    # create a soft link named link1 to a file named file1

ls -l FSOURCE_FILENAME SYMBOLIC_FILENAME   # verify new soft link 
```

## see also

- [[cp]]
- [[rm]]
- [[unlink]]
- [[ls]]
- [[find]]
- [[readlink]]
- [[brew]]
