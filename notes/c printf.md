---
tags: [c]
title: c printf
created: '2019-08-01T07:29:42.543Z'
modified: '2020-04-24T09:26:57.118Z'
---

# c printf

> formatted output conversion - `man 3 printf`

## usage
```c
printf("format", args)            /* is used to print the data onto the standard output which is often a computer monitor */

sprintf(char *, "format", args)   /* stores the formated data in a string pointed to by the char pointer */

fprintf(FILE *fp, "format", args) /* formated data is saved on a file which is pointed to by the file pointer*/
```

## see also
- [c - Difference between fprintf, printf and sprintf? - Stack Overflow](https://stackoverflow.com/a/30969793)
