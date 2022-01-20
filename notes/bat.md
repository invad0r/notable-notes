---
title: bat
created: '2022-01-18T11:18:10.918Z'
modified: '2022-01-18T11:25:11.878Z'
---

# bat

> [[cat]] clone with syntax highlighting and git integration writen [[rust]]

## install

`brew install bat`

## usage

```sh
-A      # Show and highlight non-printable characters
-n      # show line numbers (only)
```

```sh
bat FILE

bat src/*.rs          # Display multiple files at once

bat > note.md  # quickly create a new file

curl -s https://sh.rustup.rs | bat    # Read from stdin, determine the syntax automatically 
                                      # highlighting will only work if the syntax can be determined from the first line of the file
                                      # usually through a shebang such as #!/bin/sh)

yaml2json .travis.yml | json_pp | bat -l json     # Read from stdin, specify the language explicitly

bat header.md content.md footer.md > document.md    # contact files

bat f - g        # output 'f', then stdin, then 'g'.
```

## see also

- [[cat]]
- [[rust]]
