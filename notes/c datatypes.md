---
tags: [c]
title: c datatypes
created: '2019-08-19T12:57:28.967Z'
modified: '2019-08-20T07:24:43.387Z'
---

# c datatypes

[4] basic arithmetic type specifiers 
  
    char, int, float, double
    
the modifiers 

    signed, unsigned, short, long
    

## char type
| Type            |	size      |	Value range                                           |
|--               |--         |--                                                     |
| `char`          |	1 byte 	  | -128 to 127 or 0 to 255                               |
| `unsigned char` |	1 byte 	  | 0 to 255                                              |
| `signed char`   |	1 byte 	  | -128 to 127                                           |

## integer types
| Type            |	size      |	Value range                                           |
|--               |--         |--                                                     |
| `int`           |	2/4 bytes | -32,768 to 32,767 or -2,147,483,648 to 2,147,483,647  |
| `unsigned int`  |	2/4 bytes | 0 to 65,535 or 0 to 4,294,967,295                     |
| `short`         |	2 bytes   | -32,768 to 32,767                                     |
| `unsigned short`|	2 bytes   | 0 to 65,535                                           |
| `long`          |	8 bytes   | -9223372036854775808 to 9223372036854775807           |
| `unsigned long` |	8 bytes   | 0 to 18446744073709551615                             |


## floating-point types
|Type           | size    |	Value range           |	Precision         |
|--             |--       |--                     |--                 |
| `float`       |	4 byte  |	1.2E-38 to 3.4E+38    |	6 decimal places  |
| `double`      |	8 byte  |	2.3E-308 to 1.7E+308  |	15 decimal places |
| `long double` |	10 byte |	3.4E-4932 to 1.1E+4932|	19 decimal places |


## Enumerated types

    arithmetic types used to define variables that can only assign certain discrete integer value

## The type void

    void indicates that no value is available.

## Derived types

    Pointer types, Array types, Structure types, Union types, Function types
