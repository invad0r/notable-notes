---
tags: [python]
title: python comprehensions
created: '2020-01-10T13:12:15.343Z'
modified: '2020-01-11T19:08:00.354Z'
---

# python comprehensions

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
- [[python map]]
