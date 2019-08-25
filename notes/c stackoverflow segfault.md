---
tags: [c]
title: c stackoverflow segfault
created: '2019-07-30T07:58:36.045Z'
modified: '2019-08-20T07:24:43.389Z'
---

# c stackoverflow segfault

```c
#include <string.h>
#include <stdio.h>

int main(int argc, char **argv) {

  char myString[10] = "foo bar";
  puts(myString);
  printf("%s\n", myString);

  char buffer [500];
  strcpy(buffer, argv[1]);
  return 0;
}
```
