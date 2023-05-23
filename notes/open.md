---
tags: [macos]
title: open
created: '2020-03-16T16:36:43.316Z'
modified: '2023-05-19T17:56:39.627Z'
---

# open

> open files and directories on macos

## option

```sh
-a APP            # specifies app to use for opening file
-b BUNDLE_ID      # specifies the bundle identifier for app to use when opening file
-e                # causes file to be opened with /Applications/TextEdit
-t                # causes file to be opened with default text editor, as determined via LaunchServices
-f                # reads input from STDIN and opens results in the default text editor. End input by sending EOF character (type Control-D), useful for piping output to open and having it open in the default text editor
-F                # opens app "fresh," that is, without restoring windows. Saved persistent state is lost, except for Untitled documents.
-W                # causes open to wait until apps it opens (or that were already open) have exited.  Use with the -n flag to allow open to function as an appropriate app for the $EDITOR environment variable
-R                # Reveals file(s) in the Finder instead of opening them
-n                # open a new instance of app(s) even if one is already running
-g                # Do not bring app to the foreground
-j                # launches app hidden
-h                # Searches header locations for a header whose name matches the given string and then opens it.  Pass a full header name (such as NSView.h) for increased performance
-s                # For -h, partial or full SDK name to use; if supplied, only SDKs whose names contain the argument value are searched. Otherwise the highest versioned SDK in each platform is used
-u                # opens URL with whatever application claims the url scheme, even if URL also matches a file path
--args            # all remaining arguments are passed to opened app in the argv parameter to main()
--env NAME=VALUE  # adds VAR to the environment of the launched app
--stdin PATH      # launches app with STDIN  connected to PATH
--stdout PATH     # launches app with STDOUT connected to PATH
--stderr PATH     # launches app with STDERR connected to PATH
```

## usage

```sh

open .                      # open current dir in Finder

open http://host            # opens the URL in the default browser

open -a KeyboardViewer      # opens keyboardviwer :)

open -a /Applications/TextEdit.app '/Volumes/Macintosh HD/foo.txt'  # opens the document in TextEdit
open -b com.apple.TextEdit '/Volumes/Macintosh HD/foo.txt'          # opens the document in TextEdit
open -e '/Volumes/Macintosh HD/foo.txt'                             # opens the document in TextEdit

open 'file://localhost/Volumes/Macintosh HD/foo.txt'          # opens the document in the default application for its type (as determined by LaunchServices).
open 'file://localhost/Volumes/Macintosh HD/Applications/'    # opens that directory in the Finder.

ls | open -f      # pip STDOUT to file in `/tmp` and opens file in default text editor
```

## see also

- [[mdfind]]
- [[defaults]]
- [[launchctl]]
