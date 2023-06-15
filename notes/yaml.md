---
tags: [Notebooks]
title: yaml
created: '2019-07-30T06:19:49.267Z'
modified: '2023-05-24T11:35:21.366Z'
---

# yaml

> `y`aml `a`in't `m`arkup `l`anguage - is a human friendly data serialization standard for all programming languages

## usage

```yml
%YAML 1.2     # directive
---           # separate directives from document content, also serves to signal start of doc if no directives are present
foo: bar
...           # indicate end of document without starting a new one, for use in communication channels
```

## collection types: maps / dictionaries

```yml
val:
  sval: "bar"
  bval: true
```
## collection types: sequence / arrays

```yml
val:
- sval=bar
- bval=true   # true is not evaluated at first !
```

# block scalars

```yml
Block Style Indicator:
- literal: `|`
- float: `>`

Block Chomping Indicator:
- strip: `-`
- keep: `+`


example: | \n   # Keep newlines (literal)
  some text.

example: > \n   # Replace newlines with spaces (folded)
  some text

example: |      # Single newline at end   (clip)
example: >-     # No newline at end       (strip)
example: |+     # All newlines from end   (keep)


example: >3     # indendation indicator
```

## see also

- [[json]]
- [[yq]], [[jq]]
- [[heredoc]]
- [[python]], [[ruby]], [[javascript]], [[go]]
- [[kubectl]], [[docker-compose]]
- [yaml.org/](https://yaml.org/)
- [yaml-multiline.info](https://yaml-multiline.info/)
