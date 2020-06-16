---
tags: [bash/keyword]
title: bash function
created: '2019-07-30T06:19:49.008Z'
modified: '2020-05-05T06:53:21.730Z'
---

# bash function

The function refers to passed arguments by position (positional parameters).
`$@` expands positional params to seperate words: `$1` `$2`..`$N`
`$*`  expands positional params to one words: `$1c$2c..` `c` is the first character of `IFS`
`$#` holds the number of positional parameters.

## usage
```sh
function func() {
  return 0;
}

func() (             # run function as subshell
  echo 0;
)


unset -f functname  # deletes a function definition

declare -f          # displays all defined functions in your login session


# simple bash database - usage: source db.sh
db_set() { echo "$1,$2" >> database; }        
db_get() { grep "^$1," database | sed -e "s/^$1,//" | tail -n 1; }
```

## variables
```sh
${FUNCNAME[0]}    # Current function

${FUNCNAME[1]}    # Parent function

${FUNCNAME[2]}    # So on and so forth

${FUNCNAME[@]}    # All functions including parents
```

## see also
- [[bash]]
- [[bash return]]
- [[bash local]]
- [[bash parameter expansion]]
- [arguments - What is $@ in Bash? - Stack Overflow](https://stackoverflow.com/a/3898681/2087704)
- [Log-structured storage - Julia Evans](https://jvns.ca/blog/2017/06/11/log-structured-storage/)
