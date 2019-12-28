---
tags: [python]
title: python
created: '2019-07-30T06:19:49.222Z'
modified: '2019-12-26T11:24:19.589Z'
---

# python

## usage
```sh
python                  # start repl


python -m MODULE                                           # run library module as a script

python -m json.tool < <(echo '{"foo":"bar", "val": 1}')    # pretty print json


python -c CMD_STRING                                                      # program passed in as string

python -c 'import yaml,sys; yaml.safe_load(sys.stdin)' < yamltest.txt     # validate yaml

python -c 'import sys,json; print json.load(sys.stdin)[0]["Name"]' < <(docker network inspect terraform_default)
```

```python
dict(foo="bar", person="alice")       # constructor to make a new dictionary

yield     # statement used like 'return' which returns a generator object
```

## see also
- [[pip]]
- [[pyenv]]
- [[virtualenv]]
