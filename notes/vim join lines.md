---
tags: [vim]
title: vim join lines
created: '2019-07-31T06:11:23.688Z'
modified: '2019-08-26T08:43:21.863Z'
---

# vim join lines

<kbd>ggVGJ</kbd> 
- go to top of file, visually select to end of file and join lines

<kbd>qqqqqJ@qq@q</kbd>
- first three <kbd>q</kbd>'s clear the `q` register
- <kbd>qqJ@qq</kbd> records a macro to the `q` register that performs a Join, then calls `q`
- the last `@q` runs it.

```sh
:1, 21 j   # join line 1 to 21

:%s/\n/ /g # subst line break with space
```

## see also
- [[vim substitute]]


