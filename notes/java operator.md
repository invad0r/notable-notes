---
title: java operator
created: '2020-06-25T10:46:37.541Z'
modified: '2020-06-25T11:01:36.939Z'
---

# java operator

## usage
Larger number means higher precedence.
Precedence | Operator | Type | Associativity
--         |--        |--    |--
15 | `()`, `[]`, `.`  |	Parentheses, Array subscript, Member selection   | Left to Right
14 | `++`, `--`       | Unary post-increment, Unary post-decrement 	     | Right to left
13 | `++`, `--`, `+`, `-`, `!`, `~`, `(type)` | Unary pre-increment, Unary pre-decrement, Unary plus, Unary minus, Unary logical negation, Unary bitwise complement, Unary type cast | Right to left
12 | `*`, `/`, `%`        |	Multiplication, Division, Modulus | Left to right
11 | `+`, `-`             | Addition Subtraction |	Left to right
10 | `<<`, `>>`, `>>>`    |	Bitwise left shift, Bitwise right shift with sign extension, Bitwise right shift with zero extension |	Left to right
9  | `<`, `<=`, `>`, `>=`, `instanceof` | Relational less than, Relational less than or equal, Relational greater than, Relational greater than or equal, Type comparison (objects only) |	Left to right
8  | `==`, `!=` | Relational is equal to, Relational is not equal to |	Left to right
7  | `&`        | Bitwise AND          |	Left to right
6  | `^`	      | Bitwise exclusive OR |	Left to right
5  | `|`        |	Bitwise inclusive OR |	Left to right
4  | `&&` 	    | Logical AND          |	Left to right
3  | `||`       |	Logical OR           |	Left to right
2  | `?`, `:`   |	Ternary conditional 	| Right to left
1  | `=`, `+=`, `-=`, `*=`, `/=`, `%=` | 	Assignment, Addition assignment, Subtraction assignment, Multiplication assignment, Division assignment, Modulus assignment 	| Right to left

## see also
- [cs.bilkent.edu.tr/.../CS101/op_precedence.html](http://www.cs.bilkent.edu.tr/~guvenir/courses/CS101/op_precedence.html)
