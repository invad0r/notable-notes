---
tags: [c]
title: string.h
created: '2020-05-16T11:30:47.882Z'
modified: '2023-03-22T09:24:31.654Z'
---

# string.h

> defines one variable type, one macro, and various functions for manipulating arrays of characters.

## usage
```c
/* values */
size_t            /* unsigned integral type and is the result of the sizeof keyword */

/* macros */
NULL              /* macro is the value of a null pointer constant */

/* functions */
/*
 * returns number of characters in string, not including the nul character 
 * used on `char *` instead of `char []`
 */
size_t strlen(const char *s);

/*
 * compare two strings
 * a == b 	strcmp(a, b) == 0
 * a < b 	  strcmp(a, b) < 0
 * a >= b 	strcmp(a, b) >= 0
 */
int strcmp(const char *s1, const char *s2);
int strncmp(const char *s1, const char *s2, size_t n); /* compares only the first (at most) n bytes of s1 and s2. */

/*
 * dest = source
 */
char *strcpy(char *dest, const char *src);
char *strncpy(char *dest, const char *src, size_t n);
strcpy(dest, source)

/* 
 * cats the contents of source to end of dest 
 */
char *strcat(char *dest, const char *src)
strcat(dest, source)
```
## see alos
- [[c include]]
