---
tags: [bash]
title: bash globbing
created: '2019-07-30T06:19:49.009Z'
modified: '2019-08-29T12:23:39.830Z'
---

# bash globbing

> wildcards aka `pathname-expansion` refered to as globbing.

pathname-expansion `expands`: 
- `*`
- `?`
-  `.` 
- `[..]`
```sh
# wildcards:

#  * - Matches any string, including the null string
# List all JPEG files
ls *.jpg

#  ? - Matches any single (one) character.
# List JPEG files with 1 char names (eg a.jpg, 1.jpg)
ls ?.jpg

# [...] - Matches any one of the enclosed characters.
# Remove JPEG files that start with a capital letter
rm [A-Z]*.jpg

```

```sh
man bash           # some globbing explained
```

## extended globbing
```sh
?(pattern-list)     # Matches zero or one occurrence of the given patterns
*(pattern-list)     # Matches zero or more occurrences of the given patterns
+(pattern-list)     # Matches one or more occurrences of the given patterns
@(pattern-list)     # Matches one of the given patterns
!(pattern-list)     # Matches anything except one of the given patterns
```

## dotglob

If set, bash includes filenames beginning with a `.` in the results of pathname expansion.

```sh
shopt -s extglob          # set extended globbint

shopt -u dotglob          # unset dotglob
```


## extglob

If set, the extended pattern matching features described above under Pathname Expansion are enabled.

[Path name expansion - Linux Shell Scripting Tutorial - A Beginner's handbook](http://bash.cyberciti.biz/guide/Path_name_expansion)


```sh
echo file{1,2,3}.txt

ls -l /etc/{resolv.conf, passwd}
```


