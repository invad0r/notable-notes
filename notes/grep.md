---
tags: [grep, linux]
title: grep
created: '2019-07-30T06:19:49.077Z'
modified: '2019-10-24T05:47:38.762Z'
---

# grep

## usage
```sh
grep -l 'pattern' file                     # show only matching filename

find | grep 'pattern' file /dev/null       # show filename with find !
```

```sh
# Miscellaneous
-s, --no-messages         suppress error messages
-v, --invert-match        select non-matching lines

# Output control:
-m, --max-count=NUM       stop after NUM selected lines
-n, --line-number         print line number with output lines
    --line-buffered       flush output on every line
-H, --with-filename       print file name with output lines
-h, --no-filename         suppress the file name prefix on output
    --label=LABEL         use LABEL as the standard input file name prefix
  
-o, --only-matching       show only nonempty parts of lines that match
-q, --quiet, --silent     suppress all normal output
    --binary-files=TYPE   assume that binary files are TYPE: 'binary', 'text', or 'without-match'
  
-a, --text                    equivalent to --binary-files=text
-I                            equivalent to --binary-files=without-match
-d, --directories=ACTION      how to handle directories;
                              ACTION is 'read', 'recurse', or 'skip'
-D, --devices=ACTION          how to handle devices, FIFOs and sockets;
                              ACTION is 'read' or 'skip'
-r, --recursive               like --directories=recurse
-R, --dereference-recursive   likewise, but follow all symlinks
    --include=GLOB            search only files that match GLOB (a file pattern)
    --exclude=GLOB            skip files and directories matching GLOB
    --exclude-from=FILE       skip files matching any file pattern from FILE
    --exclude-dir=GLOB        skip directories that match GLOB
-L, --files-without-match     print only names of FILEs with no selected lines
-l, --files-with-matches      print only names of FILEs with selected lines
-c, --count                   print only a count of selected lines per FILE
-T, --initial-tab             make tabs line up (if needed)
-Z, --null                    print 0 byte after FILE name

# Pattern selection and interpretation
-E, --extended-regexp     PATTERNS are extended regular expressions
-F, --fixed-strings       PATTERNS are strings
-G, --basic-regexp        PATTERNS are basic regular expressions
-P, --perl-regexp         PATTERNS are Perl regular expressions
-e, --regexp=PATTERNS     use PATTERNS for matching
-f, --file=FILE           take PATTERNS from FILE
-i, --ignore-case         ignore case distinctions
-w, --word-regexp         match only whole words
-x, --line-regexp         match only whole lines
-z, --null-data           a data line ends in 0 byte, not newline
```

## see also
- [[grep regex]]
