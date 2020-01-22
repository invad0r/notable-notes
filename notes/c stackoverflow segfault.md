---
tags: [c]
title: c stackoverflow segfault
created: '2019-07-30T07:58:36.045Z'
modified: '2020-01-21T09:48:06.719Z'
---

# c stackoverflow segfault

> A segmentation fault occurs when a program attempts to access a memory location that it is not allowed to access, or attempts to access a memory location in a way that is not allowed (for example, attempting to write to a read-only location, or to overwrite part of the operating system)

## example
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

> Dangling Reference (pointer) problem means that trying to access an object or variable whose contents have already been deleted from memory, e.g:
```c
int *arr = new int[20];
delete arr;
cout<<arr[1];  //dangling problem occurs here
```

## see also
- [[signal]] `SIGSEGV`
