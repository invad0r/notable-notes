---
tags: [bsdmainutils]
title: hexdump
created: '2020-09-03T09:04:56.444Z'
modified: '2020-09-03T09:12:10.167Z'
---

# hexdump

## usage
```sh
hexdump -b FILE

hexdump -c FILE

hexdump -C FILE

hexdump -d FILE

hexdump -n length FILE


echo hello | hexdump -v -e '/1 "%02X "' ;         # hex bytes: "68 65 6C 6C 6F 0A"

echo hello | hexdump -e '8/1 "%02X ""\t"" "' -e '8/1 "%c""\n"' # same, with ASCII section

echo hello | hexdump -v -e '"x" 1/1 "%02X" " "' ;       #  preceding x: x68 x65 x6C x6C x6F x0A

echo hello | hexdump -v -e '/1 "%02X\n"'                # one hex byte per line
```

## see also
- [[xxd]]
- [[od]]
