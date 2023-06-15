---
tags: [python]
title: python
created: '2019-07-30T06:19:49.222Z'
modified: '2023-05-25T11:43:03.986Z'
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

## switch ? use dictionary mapping

```py
def numbers_to_strings(argument):
    switcher = {
        0: "zero",
        1: "one",
        2: "two",
    }
    return switcher.get(argument, "nothing")
```

[daniel.feldroy.com/posts/why-doesnt-python-have-switch-case](https://daniel.feldroy.com/posts/why-doesnt-python-have-switch-case)

## dict

> constructor to make a new dictionary

```python
dict(foo="bar", person="alice")       # constructor to make a new dictionary
```

## iter

> Return an iterator object

```python
foo = iter({'foo': 'bar', 'age': 10})

next(foo)
```

## python comprehensions

> comprehensions are a tool for transforming one list, set or dict into another list, set or dict
> syntactic sugar for a `filter` followed by a `map`

## usage

```sh
 [ e**2 for e in a_list if type(e) == types.IntType ]   # list comprehension
# └─┬─┘└───────┬───────┘└─────────────┬─────────────┘
# output       │                      │
#   iterate through intput sequence   │
#                           optional predicate
#
# a_list = [1, ‘4’, 9, ‘a’, 0, 4]  => [ 1, 81, 0, 16 ]


{ name[0].upper() + name[1:].lower() for name in names if len(name) > 1 }   # set comprehension

# names = [ 'Bob', 'JOHN', 'alice', 'bob', 'ALICE', 'J', 'Bob' ] => { 'Bob', 'John', 'Alice' }



{ k.lower() : mcase.get(k.lower(), 0) + mcase.get(k.upper(), 0) for k in mcase.keys() }   # dict comprehension

# mcase = {'a':10, 'b': 34, 'A': 7, 'Z':3}
# mcase_frequency == {'a': 17, 'z': 3, 'b': 34}
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
