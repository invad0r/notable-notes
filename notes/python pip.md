---
tags: [lang/python]
title: python pip
created: '2019-08-02T07:21:18.995Z'
modified: '2019-08-02T07:21:39.043Z'
---

# python pip

### install
```sh
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py --force-reinstall
```
[python - How do I install pip on macOS or OS X? - Stack Overflow](https://stackoverflow.com/questions/17271319/how-do-i-install-pip-on-macos-or-os-x)
[How to install and use pip without sudo or admin on macOS · GitHub](https://gist.github.com/haircut/14705555d58432a5f01f9188006a04ed)

### install packages
```sh
pip install virtualenv --verbose    # --versbose see where package gets installed to


pip install PAKCAGE --user        # avoid "Operation not permitted" and using sudo

pip list
```
