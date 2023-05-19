---
tags: [linux, macos, Notebooks]
title: ascii
created: '2019-07-30T06:19:48.987Z'
modified: '2023-05-19T11:04:19.568Z'
---

# ascii

> `american standard code for infromation interchange` - character `encoding` standard

`codepoint` - numeric value that maps to a character
`codespace` - set of all codepoints

ascii is comprised of 128 `codepoints` from `0x00` to `0x7F`

## install

```sh
brew install ascii
```

## option

```sh
-t  # one-line output  
-a  # vertical format
-d  # Decimal table  
-o  # octal table  
-x  # hex table  
-b  # binary table
-h  # This help screen 
-v  # version information
```

## usage

```sh
ascii -x      # get table in hex

man 7 ascii   # table hexadecimal
```

```
char | oct | hex | dec
"    | 042 | 22  | 34
J    | 112 | 4a  | 74
```

## hex

```
00 nul   01 soh   02 stx   03 etx   04 eot   05 enq   06 ack   07 bel
08 bs    09 ht    0a nl    0b vt    0c np    0d cr    0e so    0f si
10 dle   11 dc1   12 dc2   13 dc3   14 dc4   15 nak   16 syn   17 etb
18 can   19 em    1a sub   1b esc   1c fs    1d gs    1e rs    1f us
20 sp    21  !    22  "    23  #    24  $    25  %    26  &    27  '
28  (    29  )    2a  *    2b  +    2c  ,    2d  -    2e  .    2f  /
30  0    31  1    32  2    33  3    34  4    35  5    36  6    37  7
38  8    39  9    3a  :    3b  ;    3c  <    3d  =    3e  >    3f  ?
40  @    41  A    42  B    43  C    44  D    45  E    46  F    47  G
48  H    49  I    4a  J    4b  K    4c  L    4d  M    4e  N    4f  O
50  P    51  Q    52  R    53  S    54  T    55  U    56  V    57  W
58  X    59  Y    5a  Z    5b  [    5c  \    5d  ]    5e  ^    5f  _
60  `    61  a    62  b    63  c    64  d    65  e    66  f    67  g
68  h    69  i    6a  j    6b  k    6c  l    6d  m    6e  n    6f  o
70  p    71  q    72  r    73  s    74  t    75  u    76  v    77  w
78  x    79  y    7a  z    7b  {    7c  |    7d  }    7e  ~    7f del
```

## see also

- [[bash printf]]
- [[bash echo]]
- [[man]]
- [[od]]
- [[xxd]]
- [[iconv]]
- [[baudot]]
- [[markdown]]
- [[url encoding]]
- [[hyper text transfer protocol]]
- [asciimoji.com](http://asciimoji.com/)
- [asciiflow.com](https://asciiflow.com/#/)
- [jafrog.com/2013/11/23/colors-in-terminal](http://jafrog.com/2013/11/23/colors-in-terminal.html)
