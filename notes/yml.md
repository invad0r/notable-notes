---
tags: [yml]
title: yml
created: '2019-07-30T06:19:49.267Z'
modified: '2019-08-25T20:13:08.408Z'
---

# yml

`yaml`

- `---` are used to signal the start of a document
- serves to signal the start of a document if no directives are present.

## collection types
```yml
# maps / dictionaries
val:
  sval: "bar"
  bval: true
  
# sequence / arrays
val:
- sval=bar
- bval=true   # true is not evaluated at first !
```

## Block Scalars

Block Style Indicator
- literal: `|`
- float: `>`

Block Chomping Indicator
- strip: `-`
- keep: `+`


```sh
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
- [yaml.org/spec/1.2](https://yaml.org/spec/1.2/spec.pdf)
- [YAML Multiline Strings](https://yaml-multiline.info/)
- [[heredoc]]

