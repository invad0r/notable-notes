---
tags: [shell/bash]
title: bash arithmetic expansion
created: '2019-07-30T06:19:48.992Z'
modified: '2022-04-06T11:38:20.902Z'
---

# bash arithmetic expansion

>  most (if not all) GNU/Linux shells only perform `integer` operations.

## usage

```sh
$((EXPRESSION))       # is arithmetic expansion; return result

((EXPRESSION))        # don't return result; e.g. variable assignment
```

```sh
((var=1+2))           # Simple math

((var++))
((var--))
((var+=1))
((var-=1))


((var=var2*arr[2]))   # Using variables


echo $((13380009932/1024/1024/1024))

echo $((13380009932/1024**3))   # 1024 to the power of 3
```

## see also

- [[bc]]
- [[expr]]
- [[bash let]]
- [[bash printf]]
- [[bash let.md]]
- [[bash for]]
- [[bash braces]]
- [How can I do division with variables ? - Stack Overflow](https://stackoverflow.com/a/18093887)
- [How to Add Calculations to a Bash Script](https://www.lifewire.com/arithmetic-in-bash-2200566)
- [What is the difference between bcl and expr? Stack Exchange](https://unix.stackexchange.com/a/327468)
