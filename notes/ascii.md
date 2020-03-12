---
title: ascii
created: '2019-07-30T06:19:48.987Z'
modified: '2020-03-02T07:38:33.933Z'
---

# ascii

> `american standard code for infromation interchange` - character `encoding` standard for electronic communication

## usage
```sh
man ascii   # table hexadecimal

for ((i=32;i<127;i++)) do printf "\\$(printf %03o "$i")"; done printf "\n"    # print all avail. characters


# get decimal-set
echo '"' | tr -d "\n" | od -An -t uC
#          |            └────────────────  Use od (octal dump) to print:
#          |                                   -An    means Address none
#    remove "newline" char                     -t     select a type
#                                                  u  type is unsigned decimal.
#                                                  C  of size (one) char


printf '\112' # or 
echo $'\112'  # octal 
 
printf '\x4a' # hex
 
printf "\\$(printf %o 74)" # or 

xxd -r <<<'0 4a'           # decimal
```

char | oct | hex |dec
:--  | :-- | :-- |:--
`"`  | 042 | 22  | 34
`J`  | 112 | 4a  | 74

## see also
- [[url encoding]]
- [[ascii character set]]
- [[xxd]]
- [[od]]
- [Jafrog's dev blog](http://jafrog.com/2013/11/23/colors-in-terminal.html)
- http://asciimoji.com/
