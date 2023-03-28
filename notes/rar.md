---
tags: [linux, macos]
title: rar
created: '2023-01-27T09:01:58.297Z'
modified: '2023-03-25T12:26:05.034Z'
---

# rar

## install

```sh
brew install rar
```

## commands

```sh
a               # Add files to archive
c               # Add archive comment
ch              # Change archive parameters
cw              # Write archive comment to file
d               # Delete files from archive
e               # Extract files without archived paths
f               # Freshen files in archive
i[par]=<str>    # Find string in archives
k               # Lock archive
l[t[a],b]       # List archive contents [technical[all], bare]
m[f]            # Move to archive [files only]
p               # Print file to stdout
r               # Repair archive
rc              # Reconstruct missing volumes
rn              # Rename archived files
rr[N]           # Add data recovery record
rv[N]           # Create recovery volumes
s[name|-]       # Convert archive to or from SFX
t               # Test archive files
u               # Update files in archive
v[t[a],b]       # Verbosely list archive contents [technical[all],bare]
x               # Extract files with full path
```

## usage

```sh
tar               # print commands and switches

unrar x FILE
unrar l FILE.rar                         # list content
unrar e FILE.rar DIR/FILE DESTINATION/   # extract single file
```

## see also

- [[7z]]
- [[zip]]
- [[tar]]
