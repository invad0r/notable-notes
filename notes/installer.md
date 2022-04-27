---
tags: [macos]
title: installer
created: '2020-06-10T09:03:37.546Z'
modified: '2022-04-06T08:37:14.754Z'
---

# installer

> system software and package installer tool

## flags

```sh
-dominfo                # displays list of domains into which a package can be installed e.g. LocalSystem or CurrentUserHomeDirectory
-volinfo                # displays list of volumes onto which a package can be installed
-pkginfo                # displays list of packages that can be installed onto the target volume
-query flag             # queries package for information about the metadata
-allowUntrusted         # allow install of a package signed by an untrusted/expired certificate
-dumplog                # detailed log information is always sent to syslog using the LOG_INSTALL facility (/var/log/install.log) additionally writes stderr
-help                   # displays the help screen describing the list of parameters
-verbose                # displays more descriptive information than the default output.  Use in conjunction with -pkginfo and -volinfo information requests to see more readable output
-verboseR               # displays same information as -verbose except output is formatted for easy parsing
-vers                   # displays the version of this command
-config                 # formats installation arguments for later use. sent to stdout, no actuall installation performed
-plist                  # formats the installer output into an XML file, which is sent by default to stdout.  Use this parameter for -dominfo, -volinfo, and -pkginfo
-file pathToFile        # specifies path to the XML file containing parameter information in the key/value dictionary
-lang ISOLanguageCode   # default language of installed system (ISO format)
-listiso                # display the list of valid ISO language codes the installer recognizes
-showChoiceChangesXML   # prints to stdout the install choices for the package (specified with -pkg) in an XML format
-showChoicesXML         # prints to stdout the install choices for the package (specified with -pkg) in a hierarchical XML format. This is not the same format as used with -applyChoiceChangesXML
-store                  # install the product archive specified by -package, in the same way that it would be installed through the Mac App Store
```

## usage

```sh
installer -pkg ./AWSCLIV2.pkg -target /

installer -pkg ~/Documents/Foo.pkg -target / -config > /tmp/configfile.plist

installer -file /tmp/configfile.plist

installer -dominfo -pkg InstallMe.pkg

installer -volinfo -pkg InstallMe.pkg

installer -pkginfo -pkg DeveloperTools.mpkg

installer -pkg OSInstall.mpkg -target LocalSystem

installer -pkg OSInstall.mpkg -target / -lang en

installer -pkg DeveloperTools.mpkg -target /

installer -pkg InstallMe.pkg -target "/Volumes/Macintosh HD2"

installer -pkg InstallMe.pkg -file /tmp/InstallConfigFile

installer -pkg InstallMe.pkg -target /dev/disk0s5
```

## see also

- [[aws]]
