---
tags: [c]
title: c
created: '2019-08-19T12:57:28.967Z'
modified: '2023-05-19T11:32:30.888Z'
---

# c

> general-purpose, procedural language supporting structured programming, lexical variable scope, and recursion, with a static type system
> imperative procedural language. designed to be compiled to provide low-level access to memory and language constructs that map efficiently to machine instructions, all with minimal runtime support

## types

> 4 basic arithmetic type specifiers: `char`, `int`, `float`, `double`
> and modifiers: `signed`, `unsigned`, `short`, `long`

```c
/* char type */ 
         char             /* 1%c            1 byte  -128 to 127 or 0 to 255  */
signed   char             /* 1%c            1 byte  -128 to 127              */
unsigned char             /* 1%c            1 byte     0 to 255              */

/* integer types */
          int             /* 2/4%d          2/4 bytes  -32,768 to 32,767 or -2,147,483,648 to 2,147,483,647 */
unsigned  int             /* 2/4%u          2/4 bytes        0 to 65,535 or 0 to 4,294,967,295              */
short     int             /* 2 %hd          2 bytes    -32,768 to 32,767                                    */
unsigned short            /*                2 bytes          0 to 65,535                                    */
long int                  /* 4/8%li         8 bytes -9223372036854775808 to 9223372036854775807             */
long long int             /* 8 %lli         */
unsigned long int         /* 4%lu           8 bytes                    0 to 18446744073709551615            */
unsigned long long int    /* 8%llu          */


/*    floating-point types      */
float                     /* 4%f              4 byte   	  1.2E-38 to 3.4E+38     	6 decimal-places  */
double                    /* 8%lf             8 byte   	 2.3E-308 to 1.7E+308   	15 decimal-places */
long double               /* 0/12 or 16%Lf    10 byte  	3.4E-4932 to 1.1E+4932  	19 decimal-places */

/* Enumerated types */
/*    arithmetic types used to define variables that can only assign certain discrete integer value */

/* void type */
void                    /* void indicates that no value is available.  */

/* derived types */
/*    Pointer types, Array types, Structure types, Union types, Function types  */
int **test              /* pointer to a pointer */
```

[[typing]]

## string memory

```c
const char *str    = "Stack";           // Static     Read-only      Code segment
char *str          = "Stack";           // Static     Read-only      Code segment
char *str          = malloc(...);       // Dynamic    Read-write     Heap
char str[]         = "Stack";           // Static     Read-write     Stack
char strGlobal[10] = "Global";          // Static     Read-write     Data Segment (R/W)
```

[stackoverflow.com/a/16021546/14523221](https://stackoverflow.com/a/16021546/14523221)

## see also

- [[man]]
- [[libc]]
- [[asm]], [[wasm]]
- [[clang]]
- [[typesystem]]
- [[sqlite]]
- [[rust]], [[rustc]], [[cargo]]

