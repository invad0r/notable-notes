---
tags: [python]
title: pip
created: '2019-08-02T07:21:18.995Z'
modified: '2019-08-28T22:10:05.583Z'
---

# pip

## install
```sh
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py --force-reinstall
```

## list
```sh
pip list
```

## install packages
```sh
pip install virtualenv --verbose    # --versbose see where package gets installed to

pip install PAKCAGE --user          # avoid "Operation not permitted" and using sudo
```

## see also
- [[curl]]
- [How do I install pip on macOS or OS X? - Stack Overflow](https://stackoverflow.com/questions/17271319/how-do-i-install-pip-on-macos-or-os-x)
- [How to install and use pip without sudo - GitHub](https://gist.github.com/haircut/14705555d58432a5f01f9188006a04ed)
