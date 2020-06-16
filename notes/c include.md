---
tags: [c]
title: c include
created: '2020-04-24T09:16:35.459Z'
modified: '2020-04-24T09:24:14.325Z'
---

# c include

> `#include` directive shall identify a header or source file that can be processed by the implementation

## usage
```c
#include <filename> /* preprocessor search in -I directories and in predefined directories first, then in the .c file's directory */

#include "filename" /* preprocessor search the source directory first, and then revert to -I and predefined */
```
## see also
- [[gcc]]
- [[nm]]
- [[ld]]
- [[ldd]]
- [stackoverflow.com/how-are-implementations-of-stdlib-functions-stored-and-linked](https://stackoverflow.com/a/24920452/2087704)
- [c standard](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n1570.pdf#page=182)
