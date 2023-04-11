---
tags: [linux, macos]
title: zip
created: '2019-09-26T06:55:59.693Z'
modified: '2023-03-13T11:20:49.550Z'
---

# zip

> package and compress (archive) files

## zip

## option

```sh
-r, --recurse-paths      # travel the directory structure recursively

-R, --recurse-patterns   # travel the directory structure recursively starting at the current directory; for example:
```

## usage

```sh
zip -r foo.zip foo 
zip -r foo foo          # all the files and directories in foo are saved in a zip archive named foo.zip, including files with names starting with "."
                        # recursion does not use shell's file-name substitution mechanism
      
zip -r foo foo1 foo2    # multiple source directories, which first zips up foo1 and then foo2, going down each directory

zip -r FILE.zip FILE/   # recursively zip all files in dir

zip -R foo "*.c"        # all the files matching *.c in the tree starting at the current directory are stored into a zip archive foo.zip.  
                        # Note: that *.c will match file.c, a/file.c and a/b/.c
                        # More than one pattern can be listed as separate arguments

zip -d FILE.jar BOOT-INF/classes/logback/logback-spring.xml   # remove file out of jar
```

## unzip

## option

> list, test and extract compressed files in a zip archive

```sh
-c     # extract files to stdout; similar to the -p option except that the name of each file is printed as it is extracted
-p     # extract files to pipe (stdout).  Nothing but the file data is sent to stdout, and the files are always extracted in binary format

-l     # list archive files in short format
-v     # list verbosely or show version info
-z     # display only the archive comment

-t     # test archive files.  This option extracts each specified file in memory and compares the CRC 
       # (cyclic redundancy check, an enhanced checksum) of the expanded file with the original file's stored CRC value

-f     # freshen existing files, extract only those files that already exist on disk and that are newer than the disk copies
-u     # update existing files and create new ones if needed. same as -f option and in addition it extracts files that do not already exist on disk
```

## usage

```sh
unzip FILE.zip

unzip -l FILE.jar                            # list files of jar

unzip -v FILE.zip                            # list more verbose

unzip -p FILE.jar META-INF/MANIFEST.MF       # get current versions
```

## see also

- [[rar]]
- [[gzip]]
- [[zcat]]
- [[tar]]
- [[zrun]]
- [[jar]]
