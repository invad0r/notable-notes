---
tags: [c, vcs]
title: gource
created: '2023-06-01T05:23:19.923Z'
modified: '2023-06-01T05:50:50.553Z'
---

# gource

## install

```sh
brew install gource
```

## option

```sh
-h, --help                          # help, '-H' for extended help
-WIDTHxHEIGHT, --viewport WxH       # set the viewport size. If -f is also supplied, will attempt to set the video mode to this also. Add ! to make the window non-resizable
    --screen SCREEN                 # set the number of the screen to display on
    --high-dpi                      # request a high DPI display when creating the window
    --window-position XxY           # Initial window position on your desktop which may be made up of multiple monitors
    --frameless                     # frameless window
-f, --fullscreen                    # Fullscreen
-w, --windowed                      # Windowed
    --transparent                   # Make the background transparent. Only really useful for screenshots
    --start-date FORMAT             # start with the first entry after the supplied date and optional time, If a time zone offset isn't specified the local time zone is used
    --stop-date FORMAT              # Stop after the last entry prior to the supplied date and optional time
-p, --start-position POSITION       # Begin at some position in the log (between 0.0 and 1.0 or 'random')
    --stop-position  POSITION       # Stop (exit) at some position in the log (does not work with STDIN)
-t, --stop-at-time SECONDS          # Stop (exit) after a specified number of seconds
    --stop-at-end                   # Stop (exit) at the end of the log / stream
    --loop                          # Loop back to the start of the log when the end is reached
    --loop-delay-seconds            # Seconds to delay before looping
-a, --auto-skip-seconds SECONDS     # Skip to next entry if nothing happens for a number of seconds
-s, --seconds-per-day SECONDS       # Speed of simulation in seconds per day
    --realtime                      # Realtime playback speed
    --no-time-travel                # Use the time of the last commit if the time of a commit is in the past
-c, --time-scale SCALE              # Change simulation time scale. E.g. 0.5 for half speed, 2 for double speed
-i, --file-idle-time SECONDS        # Time in seconds files remain idle before they are removed or 0 for no limit
    --file-idle-time-at-end SECONDS # Time in seconds files remain idle at the end before they are removed
-e, --elasticity FLOAT              # Elasticity of nodes
-b, --background-colour FFFFFF      # Background colour in hex
    --background-image IMAGE        # Set a background image
    --logo IMAGE                    # Logo to display in the foreground
    --logo-offset XxY               # Offset position of the logo
    --title TITLE                   # Set a title
    --font-file FILE                # Specify the font. Should work with most font file formats supported by FreeType, such as TTF and OTF, among others
    --font-scale SCALE              # Scale the size of all fonts
    --font-size SIZE                # Font size used by the date and title
    --file-font-size SIZE           # Font size of filenames
    --dir-font-size SIZE            # Font size of directory names
    --user-font-size SIZE           # Font size of user names
    --font-colour FFFFFF            # Font colour used by the date and title in hex
    --key                           # Show file extension key
    --date-format FORMAT            # Specify display date string (strftime format)
    --log-command VCS               # Show the VCS log command used by gource (git,svn,hg,bzr,cvs2cl)
    --log-format VCS                # Specify the log format (git,svn,hg,bzr,cvs2cl,custom), Required when reading from STDIN
    --git-branch                    # Get the git log of a branch other than the current one
    --follow-user USER              # Have the camera automatically follow a particular user
    --highlight-dirs                # Highlight the names of all directories
    --highlight-user USER           # Highlight the names of a particular user
    --highlight-users               # Highlight the names of all users
    --highlight-colour FFFFFF       # Font colour for highlighted users in hex
    --selection-colour FFFFFF       # Font colour for selected users and files
    --filename-colour FFFFFF        # Font colour for filenames
    --dir-colour FFFFFF             # Font colour for directories
    --dir-name-depth DEPTH          # draw names of directories down to a specific depth in the tree.
    --dir-name-position FLOAT       # Position along edge of the directory name (between 0.1 and 1.0, default is 0.5)
    --filename-time SECONDS         # Duration to keep filenames on screen (>= 2.0)
    --file-extensions               # Show filename extensions only
    --file-extension-fallback       # Use filename as extension if the extension is missing or empty
    --file-filter REGEX             # Filter out file paths matching the specified regular expression
    --file-show-filter REGEX        # Show only file paths matching the specified regular expression
    --user-filter REGEX             # Filter usernames matching the specified regular expression
    --user-show-filter REGEX        # Show only usernames matching the specified regular expression
    --user-image-dir DIRECTORY      # Directory containing .jpg or .png images of users (eg "Full Name.png") to use as avatars
    --default-user-image IMAGE      # Path of .jpg or .png to use as the default user image
    --fixed-user-size               # Forces the size of the user image to remain fixed throughout
    --colour-images                 # Colourize user images
    --crop AXIS                     # Crop view on an axis (vertical,horizontal)
    --padding FLOAT                 # Camera view padding
    --multi-sampling                # Enable multi-sampling
    --no-vsync                      # Disable vsync
    --bloom-multiplier FLOAT        # Adjust the amount of bloom
    --bloom-intensity FLOAT         # Adjust the intensity of the bloom
    --max-files NUMBER              # Set the maximum number of files or 0 for no limit. Excess files will be discarded
    --max-file-lag SECONDS          # Max time files of a commit can take to appear, Use -1 for no limit
    --max-user-speed UNITS          # Max speed users can travel per second
    --user-friction SECONDS         # Time users take to come to a halt
    --user-scale SCALE              # Change scale of user avatars
    --camera-mode MODE              # Camera mode (overview,track)
    --disable-auto-rotate           # Disable automatic camera rotation
    --disable-input                 # Disable keyboard and mouse input
    --hide DISPLAY_ELEMENT          # hide one or more display elements: bloom, date, dirnames, files, filenames, mouse, progress, root, tree, users, usernames
    --hash-seed SEED                # Change the seed of hash function
    --caption-file FILE             # Caption file (see Caption Log Format)
    --caption-size SIZE             # Caption size
    --caption-colour FFFFFF         # Caption colour in hex
    --caption-duration SECONDS      # Caption duration
    --caption-offset X              # Caption horizontal offset (0 to centre captions)
-o, --output-ppm-stream FILE        # Output a PPM image stream to a file ('-' for STDOUT).  This will automatically hide the progress bar initially and enable 'stop-at-end'
-r, --output-framerate FPS          # Framerate of output (25,30,60). Used with --output-ppm-stream
    --output-custom-log FILE        # Output a custom format log file ('-' for STDOUT)
    --load-config CONFIG_FILE       # Load a gource conf file
    --save-config CONFIG_FILE       # Save a gource conf file with the current options
    --path PATH                     # vcs directory, a pre-generated log file, a Gource conf file or '-' to read STDIN, if omitted, will attempt to read a log from the current DIR
```

## usage

```sh
gource
```

## interactive keyboard commands

```sh
V           # Toggle camera mode
C           # Displays Gource logo
K           # Toggle file extension key
M           # Toggle mouse visibility
N           # Jump forward in time to next log entry
S           # Randomize colours
D           # Toggle directory name display mode
F           # Toggle file name display mode
U           # Toggle user name display mode
G           # Toggle display of users
T           # Toggle display of directory tree edges
R           # Toggle display of root directory edges
+-          # Adjust simulation speed
<>          # Adjust time scale
TAB         # Cycle through visible users
F12         # screenshot
Alt+Enter   # fullscreen toggle
ESC         # quit
```

## see also

- [[git]]
- [[ffmpeg]]
- [[macos keyboard shortcuts]]
- [github.com/acaudwell/Gource](https://github.com/acaudwell/Gource)

