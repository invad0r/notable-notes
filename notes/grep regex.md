---
deleted: true
tags: [grep, linux, regex]
title: grep regex
created: '2019-07-30T06:19:49.076Z'
modified: '2020-03-18T16:05:05.414Z'
---

# grep regex
```sh
# regex
# `^` (Caret)         match expression at the start of a line, as in `^A`
# `$` (Question)      match expression at the end of a line, as in `A$`  
# `\` (Back Slash)    turn off the special meaning of the next character, as in `\^`.
# `[ ]` (Brackets)    match any one of the enclosed characters, as in [aeiou]. Use Hyphen "-" for a range, as in `[0-9]`
# `[^ ]`              match any one character except those enclosed in `[ ]`, as in `[^0-9]`
# `.` (Period)        match a single character of any value, except end of line.  
# `*` (Asterisk)      match zero or more of the preceding character or expression.
# `\{x,y\}`           match x to y occurrences of the preceding.   
# `\{x\}`             match exactly x occurrences of the preceding.
# `\{x,\}`            match x or more occurrences of the preceding.

# basic regex
grep "^[^#;]" smb.conf              # filter-out-comments - http://unix.stackexchange.com/a/60995

ls -l | grep "^d"                   # list directories

ps aux | grep "[d]ockerd"           # avoid grep in output via regex: find character 'd' followed by 'ockerd'


# extended-regexp
grep -E '192.168.(230.0|231.128)'   # regular expression

grep -E "^[[:alpha:]]*:" Makefile   # get tasks frome makefile


# pcre
echo "http://foo.net/path/repo.git" | grep -o -P '(?<=https:\/\/|http:\/\/|@).*?(?=(\/|:))'
```

## see also
- [[regex]]
- [REGEX Cheat Sheet](https://staff.washington.edu/weller/grep.html)
- [Regular Expressions in grep](http://www.robelle.com/smugbook/regexpr.html)
- [ntu.edu.sg/home/ehchua/programming/howto/Regexe](https://www.ntu.edu.sg/home/ehchua/programming/howto/Regexe.html)
