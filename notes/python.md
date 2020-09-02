---
tags: [python]
title: python
created: '2019-07-30T06:19:49.222Z'
modified: '2020-09-01T08:30:56.460Z'
---

# python

## usage
```sh
python                  # start repl

python -q               # start repl without version info


python -m MODULE                                            # run library module as a script

python3 -m http.server                                      # start web server

python -m json.tool < <(echo '{"foo":"bar", "val": 1}')     # pretty print json

echo STRING | python -m base64       # encode STRING


python -c CMD_STRING                                                      # program passed in as string

python -c 'import yaml,sys; yaml.safe_load(sys.stdin)' < yamltest.txt     # validate yaml

python -c 'import sys,json; print json.load(sys.stdin)[0]["Name"]' < <(docker network inspect terraform_default)

python -c 'import sys, yaml, json; json.dump(yaml.load(sys.stdin), sys.stdout, indent=4)' < in.yaml > out.json
```

## see also
- [[irb]]
- [[pip]]
- [[pyenv]]
- [[virtualenv]]
- [[ruby]]
- [[java]]
- [[scala]]
- [[php]]
- [[yaml]]
