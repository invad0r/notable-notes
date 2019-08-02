---
tags: [lang/python]
title: python
created: '2019-07-30T06:19:49.222Z'
modified: '2019-08-02T07:21:15.653Z'
---

# python

### json
```sh
cat file.json | python -m json.tool    # pretty print json

docker network inspect monitoring_default | python -c 'import sys, json; print json.load(sys.stdin)[0]["Name"]'
```
### validate yaml
```sh
python -c 'import yaml,sys;yaml.safe_load(sys.stdin)' < yamltest.txt
```
