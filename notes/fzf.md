---
tags: [brew]
title: fzf
created: '2019-07-30T06:19:49.058Z'
modified: '2021-11-04T10:58:59.287Z'
---

# fzf

> command-line fuzzy finder

## installation

`brew install fzf`

## usage

```sh
FZF_DEFAULT_COMMAND       # default command to use when input is tty
                          # ⚠️ variable is not used by shell extensions due to the slight difference in requirements
                          # e.g. CTRL-T runs $FZF_CTRL_T_COMMAND instead, 
                          #   vim **<tab> runs _fzf_compgen_path(), 
                          #   and cd **<tab> runs _fzf_compgen_dir()
FZF_DEFAULT_COMMAND='fd --type f'

          
FZF_DEFAULT_OPTS    # default options
FZF_DEFAULT_OPTS="--layout=reverse --inline-info"
```


## key bindings

```sh
^-T     # Paste the selected files and directories onto the command-line
        # Set FZF_CTRL_T_COMMAND to override the default command
        # Set FZF_CTRL_T_OPTS to pass additional options

^-R     # Paste the selected command from history onto the command-line
        # If you want to see the commands in chronological order, press CTRL-R again which toggles sorting by relevance
        # Set FZF_CTRL_R_OPTS to pass additional options

⌥-C     # cd into the selected directory
        # Set FZF_ALT_C_COMMAND to override the default command
        # Set FZF_ALT_C_OPTS to pass additional options
```

## see also

- [github.com/junegunn/fzf#using-homebrew-or-linuxbrew](https://github.com/junegunn/fzf#using-homebrew-or-linuxbrew)
- [[tmux]]
- [[macos keyboard shortcuts]]
