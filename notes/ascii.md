---
title: ascii
created: '2019-07-30T06:19:48.987Z'
modified: '2019-08-25T19:59:01.189Z'
---

# ascii

> `ASCII - American Standard Code for Infromation Interchange` is a character `encoding`standard for electronic communication

[[url encoding]]

## ascii character set

```sh
man ascii
```

### print all avail. characters
```sh
for ((i=32;i<127;i++)) do
  printf "\\$(printf %03o "$i")"; 
done
printf "\n"
```
    
| char | oct | hex |dec |
| :--  | :-- | :-- |:-- |
| `"`  | 042 | 22  | 34 |
| `J`  | 112 | 4a  | 74 |


```sh
printf '\112' # or 
echo $'\112'  # octal 
 
printf '\x4a' # hex
 
printf "\\$(printf %o 74)" # or 
xxd -r <<<'0 4a'           # decimal
```


## get decimal-set
```sh
echo '"' | tr -d "\n" | od -An -t uC
#          |            └────────────────  Use od (octal dump) to print:
#          |                                   -An    means Address none
#    remove "newline" char                     -t     select a type
#                                              u      type is unsigned decimal.
#                                              C      of size (one) char


```

## hexdump file
```sh
xxd docker-compose.yml    # hexdump of file
```

## see also
- [Jafrog's dev blog](http://jafrog.com/2013/11/23/colors-in-terminal.html)
