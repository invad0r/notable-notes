---
tags: [python]
title: python
created: '2019-07-30T06:19:49.222Z'
modified: '2021-06-10T06:35:14.925Z'
---

# python

> interpreted, interactive, object-oriented programming language

## usage

```sh
python                  # start repl
python -q               # start repl without version info



python -m MODULE                                              # run library module as a script

python3 -m http.server                                        # start web server

python  -m json.tool < <(echo '{"foo":"bar", "val": 1}')      # pretty print json

echo STRING | python -m base64                                # encode STRING


# command strings - program passed in as string

python -c 'import sys,yaml; yaml.safe_load(sys.stdin)' < yamltest.txt     # validate yaml

python -c 'import sys,json; print json.load(sys.stdin)[0]["Name"]' < <(docker network inspect terraform_default)

python -c 'import sys,yaml,json; json.dump(yaml.load(sys.stdin), sys.stdout, indent=4)' < IN_YAML > OUT_JSON

python -c 'import sys,yaml,json; yaml.safe_dump(json.load(sys.stdin), sys.stdout, default_flow_style=False)' < IN_JSON > OUT_YAML
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
