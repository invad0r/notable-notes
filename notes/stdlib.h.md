---
tags: [c]
title: stdlib.h
created: '2020-05-16T12:10:34.736Z'
modified: '2023-03-25T12:41:05.728Z'
---

# stdlib.h

> defines four variable types, several macros, and various functions for performing general functions

## usage

```c
/* values */
size_t            /* unsigned integral type and is the result of the sizeof keyword */
wchar_t           /* an integer type of the size of a wide character constant */
div_t             /* structure returned by the div function */
ldiv_t            /* structure returned by the ldiv function */

/* macros */
NULL              /* value of a null pointer constant */
EXIT_FAILURE      /* value for the exit function to return in case of failure */
EXIT_SUCCESS      /* value for the exit function to return in case of success */
RAND_MAX          /* maximum value returned by the rand function */
MB_CUR_MAX        /* maximum number of bytes in a multi-byte character set which cannot be larger than MB_LEN_MAX */

/* functions */
int atoi(const char *str)                   /* converts string to an integer */

void *malloc(size_t size)                   /* Allocates the requested memory and returns a pointer to it */

void *calloc(size_t nitems, size_t size)    /* allocates requested memory and returns a pointer to it */

void *realloc(void *ptr, size_t size)       /* attempts to resize the memory block pointed to by ptr that was previously allocated with a call to malloc or calloc */

void free(void *ptr                         /* deallocates the memory previously allocated by a call to calloc, malloc, or realloc */

void exit(int status)                       /* Causes the program to terminate normally */

char *getenv(const char *name)              /* Searches for the environment string pointed to by name and returns the associated value to the string */

int rand(void)                              /* Returns a pseudo-random number in the range of 0 to RAND_MAX */

int system(const char *string)              /* command specified by string is passed to the host environment to be executed by the command processor */

void *bsearch                               /* Performs a binary search */
(
  const void *key, 
  const void *base, 
  size_t nitems, 
  size_t size, 
  int (*compar)(const void *, 
  const void *)
)

void qsort                                  /* Sorts an array */
(
  void *base, 
  size_t nitems, 
  size_t size, 
  int (*compar)(const void *, 
  const void*)
)
```

## see also

- [[c include]]
- [tutorialspoint.com/.../stdlib_h.htm](https://www.tutorialspoint.com/c_standard_library/stdlib_h.htm)
