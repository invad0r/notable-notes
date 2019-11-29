---
tags: [bash/keyword]
title: bash function
created: '2019-07-30T06:19:49.008Z'
modified: '2019-10-07T06:09:00.470Z'
---

# bash function

The function refers to passed arguments by position (positional parameters).
`$@` expands positional params to seperate words: `$1` `$2`..`$N`
`$*`  expands positional params to one words: `$1c$2c..` `c` is the first character of `IFS`
`$#` holds the number of positional parameters.

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

## variables
```sh
${FUNCNAME[0]}    # Current function.
${FUNCNAME[1]}    # Parent function.
${FUNCNAME[2]}    # So on and so forth.

${FUNCNAME[@]}    # All functions including parents.
```

## see also
- [[bash]]
- [arguments - What is $@ in Bash? - Stack Overflow](https://stackoverflow.com/a/3898681/2087704)
