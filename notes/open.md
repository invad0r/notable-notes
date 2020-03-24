---
tags: [macos]
title: open
created: '2020-03-16T16:36:43.316Z'
modified: '2020-03-16T16:41:42.743Z'
---

# open

> open files and directories on macos

## usage
```sh
open .            # open current dir in Finder

open http://host  # opens the URL in the default browser

open -a /Applications/TextEdit.app '/Volumes/Macintosh HD/foo.txt'  # opens the document in TextEdit

open -b com.apple.TextEdit '/Volumes/Macintosh HD/foo.txt'          # opens the document in TextEdit

open -e '/Volumes/Macintosh HD/foo.txt'                             # opens the document in TextEdit

ls | open -f      # writes output of `ls` to a file in `/tmp` and opens the file in the default text editor (as determined by LaunchServices).

open 'file://localhost/Volumes/Macintosh HD/foo.txt'          # opens the document in the default application for its type (as determined by LaunchServices).

open 'file://localhost/Volumes/Macintosh HD/Applications/'    # opens that directory in the Finder.
```

## see also
- [[-]]
