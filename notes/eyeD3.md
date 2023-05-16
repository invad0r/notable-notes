---
tags: [linux, macos, python]
title: eyed3
created: '2019-08-23T14:52:21.967Z'
modified: '2023-05-11T10:51:56.275Z'
---

# eyed3

> tagging mp3

## install

```sh
brew install eye-d3
```

## option

```sh
-h,       --help                  # show this help message and exit
          --version               # Display version information and exit
          --about                 # Display full version, release name, additional info, and exit
-r,       --recursive             # Recurse into subdirectories
          --exclude PATTERN       # A regular expression for path exclusion. May be specified multiple times
          --fs-encoding ENCODING  # Use the specified file system encoding for filenames. Default as it was detected is 'utf-8' but this option is still useful when reading from mounted file systems
-L,       --plugins               # List all available plugins
-P NAME,  --plugin NAME           # Specify which plugin to use. The default is 'classic'
-C FILE,  --config FILE           # Supply a configuration file. The default is '/Users/P00200478/.config/eyeD3/config.ini', although even that is optional
          --backup                # Plugins should honor this option such that a backup is made of any file modified. The backup is made in same directory with a '.orig' extension added
-Q,       --quiet                 # A hint to plugins to output less
          --no-color              # Suppress color codes in console output. This will happen automatically if the output is not a TTY (e.g. when redirecting to a file)
          --no-config             # do not load the default user config $HOME/.config/eyeD3/config.ini', -c/--config options are still honored if present

-l LEVEL, --log-level LEVEL       # Set a log level 'debug', 'verbose', 'info', 'warning', 'error', 'critical'
--profile                         # Run using python profiler
--pdb                             # Drop into 'pdb' when errors occur
```

## usage

```sh
eyed3 FILE.mp3                                                                # list meta info

eyed3 --artist "ARTIST" --album "ALBUM" --title "TITLE" --track "01" FILE     # add meta

eyed3 --add-image "cover.jpg:FRONT_COVER" FILE

eyeD3 --remove-all-images FILE



find . -type f -name "*.mp3" -exec eyed3 {} \;    # read metadata form all mp3's
```

## see also

- [[youtube-dl]]
- [[python]]
- [[ffmpeg]]
