---
tags: [c]
title: c operators
created: '2020-04-24T10:42:43.426Z'
modified: '2020-05-16T11:32:01.766Z'
---

# c operators

> an operator is a symbol that tells the compiler to perform a certain mathematical or logical manipulation, they are used to manipulate data and variables


## arithmetic operators
```c
+	    /* adds two operands                    */
-	    /* subtract second operands from first  */
*	    /* multiply two operand                 */
/	    /* divide numerator by denominator      */
%	    /* remainder of division                */
++	  /* Increment operator                   */
--	  /* Decrement operator                   */
```

## relational operators
```c
==	  /* Check if two operand are equal                                     */
!=	  /* Check if two operand are not equal.                                */
> 	  /* Check if operand on the left is greater than operand on the right  */
< 	  /* Check operand on the left is smaller than right operand            */
>= 	  /* check left operand is greater than or equal to right operand       */
<= 	  /* Check if operand on left is smaller than or equal to right operand */
```

## logical operators
```c
&& 	  /* Logical AND */
|| 	  /* Logical OR	 */
! 	  /* Logical NOT */
```

## bitwise operators
> perform manipulations of data at bit level
> also perform shifting of bits from right to left
> are not applied to `float` or `double`
```c
& 	/* Bitwise AND */
| 	/* Bitwise OR */
^ 	/* Bitwise exclusive OR */
    /*    truth table                       */
    /*    a 	b	  a & b	  a | b	  a ^ b     */
    /*    0 	0	  0	      0	      0         */
    /*    0 	1	  0	      1	      1         */
    /*    1 	0	  0	      1	      1         */
    /*    1 	1	  1	      1	      0         */

<< 	/* left shift */
>> 	/* right shift */

0001000 << 2 = 0100000 
0001000 >> 2 = 0000010 
```

## assignment operators
```c
 = 	  /* assigns values from right side operands to left side operand                         */
+= 	  /* adds right operand to the left operand and assign the result to left	                */
-= 	  /* subtracts right operand from the left operand and assign the result to left operand	*/
*= 	  /* mutiply left operand with the right operand and assign the result to left operand	  */
/= 	  /* divides left operand with the right operand and assign the result to left operand	  */
%= 	  /* calculate modulus using two operands and assign the result to left operand	          */
```

## conditional/ternary operators
```c
expression1 ? expression2 : expression3
```

## special operators
```c
sizeof 	/* Returns the size of an variable	    sizeof(x) return size */
& 	    /* Returns the address of an variable	  &x ; return address   */
* 	    /* Pointer to a variable	              *x ; dereference pointer  */
```

## see also
- [[string.h]] strlen

