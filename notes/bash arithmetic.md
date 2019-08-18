---
tags: [bash]
title: bash arithmetic
created: '2019-07-30T06:19:48.992Z'
modified: '2019-08-02T08:44:05.997Z'
---

# bash arithmetic

>  most (if not all) GNU/Linux shells only perform `integer` operations.

- [How can I do division with variables in a Linux shell? - Stack Overflow](https://stackoverflow.com/a/18093887)
- [How to Add Calculations to a Bash Script](https://www.lifewire.com/arithmetic-in-bash-2200566)

## printf
```sh
printf "%.3f\n" $((1+1/2))                      # 1.000

printf "%.3f\n" $( echo "1+1/2" | bc -l )       # 1.500
```


## bc

> `basic calculator` is an `arbitrary-precision calculator language`

```sh
bc -l     # -l, --mathlib: Uses the predefined math routines.

echo "3.4+7/8-(5.94*3.14)" | bc     # = -15.25

echo "2/3"                 | bc     # = 0

echo "scale=2; 2/3"        | bc     # = .66

echo "(2/3)+(7/8)"         | bc     # = 0

echo "scale=2;(2/3)+(7/8)" | bc     # = 1.53

echo "scale=4;(2/3)+(7/8)" | bc     # = 1.5416

echo "scale=6;(2/3)+(7/8)" | bc     # = 1.541666

echo "(2/3)+(7/8)" | bc -l          # = 1.54166666666666666666
```

## expr
> `evaluate expression` using only `integer` and tops out at `2^63 - 1`
```sh
expr 1 + 1           # = 2

myvar=$(expr 1 + 1)  # $myvar == 2

expr $myvar + 1      # = 3

expr $myvar / 3      # = 1

expr $myvar \* 3     # = 9
```
[What is the difference between bcl and expr? Stack Exchange](https://unix.stackexchange.com/a/327468)

## let

[[bash let.md]]
