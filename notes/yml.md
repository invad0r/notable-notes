---
tags: [yml]
title: yml
created: '2019-07-30T06:19:49.267Z'
modified: '2019-08-01T08:23:13.011Z'
---

# yml

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

[YAML Multiline Strings](https://yaml-multiline.info/)

## yq

### update inplace via script
```sh
# ../update-deploy.yml
# services.application.deploy.mode: replicated
# services.application.deploy.replicas: 0

yq w -i -s ../update.yml file.yml
```


```sh
yq r file.yml services.application.image
```
