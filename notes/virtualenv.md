---
tags: [python]
title: virtualenv
created: '2019-07-30T06:19:49.221Z'
modified: '2023-03-22T10:56:33.464Z'
---

# virtualenv

> tool to create isolated python environments

## install

```sh
pip install virtualenv --verbose
pip3 install virtualenv
```

## usage

```sh
virtualenv VIRTUALENV_NAME

source VIRTUALENV_NAME/bin/activate     # activate virtualenv in project
pip install pre-commit                  # install to virtualenv


pip3 install virtualenv
virtualenv venv --python=python3.8
source venv/bin/activate


python3 -m venv ./venv
source ./venv/bin/activate      # activate virtual env
type python pip python3 pip3    # show different paths
```

## see also

- [[python]]
- [[pip]]
- [Stack Overflow - Virtualenv Command Not Found](https://stackoverflow.com/a/36577160)
- [virtualenv.pypa.io/en/latest/](https://virtualenv.pypa.io/en/latest/)
- [[pyenv]]
- [[sam]]
