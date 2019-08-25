---
tags: [bash/keyword]
title: bash function
created: '2019-07-30T06:19:49.008Z'
modified: '2019-08-20T07:20:38.985Z'
---

# bash function

The function refers to passed arguments by position (positional parameters).
`$@` expands positional params to seperate words: `$1` `$2`..`$N`
`$*`  expands positional params to one words: `$1c$2c..` `c` is the first character of `IFS`
`$#` holds the number of positional parameters.

[arguments - What is $@ in Bash? - Stack Overflow](https://stackoverflow.com/a/3898681/2087704)

```sh
function func() {
  ..
}
```

### run function as subshell
```sh
func() (
)
```

```sh
unset -f functname  # deletes a function definition

declare -f          # displays all defined functions in your login session
```
