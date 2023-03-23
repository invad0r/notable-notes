---
tags: [python]
title: pipx
created: '2020-11-05T12:54:51.421Z'
modified: '2023-03-22T08:33:03.434Z'
---

# pipx

> install and run [[python]] apps in isolated environments

## install

```sh
brew install pipx
```

## env

```sh
PIPX_HOME                     # overrides default pipx location - virtual envs install to $PIPX_HOME/venvs
PIPX_BIN_DIR                  # overrides location of app installations - apps are symlinked/copied here
USE_EMOJI                     # overrides emoji behavior
PIPX_DEFAULT_PYTHON           # overrides default python used for commands
```

## usage

```sh
pipx list                     # List installed packages

pipx install PACKAGE
pipx install . --force

pipx reinstall PACKAGE
pipx uninstall PACKAGE
pipx upgrade PACKAGE

pipx inject                   # install packages into an existing virtual env
pipx upgrade-all              # upgrade all packages - `pip install -U <pkgname>` for each package
pipx uninstall-all            # un-install all packages
pipx reinstall-all            # re-install all packages

pipx run                      # download latest version of package to temp virtual env, then run app from it - compatible with local `__pypackages__` dir
pipx runpip                   # run pip in an existing pipx-managed virtual env
pipx ensurepath               # ensure dir necessary for pipx operation are in your PATH environment variable.
pipx completions              # print instructions on shell completions
```

## see also

- [[pyenv]]
- [[pip]]
- [[python]]
