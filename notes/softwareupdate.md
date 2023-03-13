---
tags: [macos]
title: softwareupdate
created: '2021-09-30T06:53:42.930Z'
modified: '2022-05-30T06:32:48.525Z'
---

# softwareupdate

> system software update tool

## flags

```sh
-h, --help             # print command usage
-l, --list             # list all available updates

-i, --install         # each update specified by args is downloaded and installed
-r, --recommended     # all updates that are recommended for your system - are prefixed with a * in --list output
-R, --restart         # automatically restart or shut down if required to complete installation
                      # if the user is not logged in, macOS will trigger a forced reboot if necessary. If you wish to always perform a forced reboot, pass -f (--force)
-a, --all             # all updates that are applicable to your system, including those non-recommended ones, which are prefixed with a - character in the --list output
                      # item ...    One or more specified updates. The --list output shows the item names you can specify here, prefixed by the * or - characters. See EXAMPLES.

-d, --download        # each update specified by args is downloaded but not installed. The values of args are the same as for the --install command. 
                      # updates downloaded with --download can be subsequently installed with --install, or through the App Store (as long as they remain applicable to your system).  
                      # Updates are downloaded to /Library/Updates, but are not designed to be installed by double-clicking the packages in that directory: always use --install or the App Store to actually perform the install
--schedule            # returns the per-machine automatic (background) check preference
```

## usage

```sh
softwareupdate --all --install --force
```

## see also

- [[xcode-select]]
- [[brew]]
