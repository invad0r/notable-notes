---
tags: [shell/bash/builtin]
title: bash echo
created: '2019-08-02T06:42:37.582Z'
modified: '2023-04-12T11:59:24.762Z'
---

# bash echo

> write arguments to stdout

## option

```sh
-n        # do not append a newline
-e        # enable interpretation of the following backslash escapes
-E        # explicitly suppress interpretation of backslash escapes
```

## usage

```sh
echo -n "USER:PWD" | base64     # not linebreak !
```

## url encoding

> urls can only be sent over the Internet using the ASCII character-set.

- urls often contain characters outside the `ascii` set and has to be converted into a valid `ascii` format
- url encoding replaces unsafe `ascii` characters with a `%` followed by two hexadecimal digits
- urls cannot contain spaces - encoding normally replaces a space with a `+` sign or with `%20`

```sh
# encode
echo -ne 'some random\nbytes' | xxd -plain | tr -d '\n' | sed 's/\(..\)/%\1/g'
curl -s -o /dev/null -w "%{url_effective}\n" --get --data-urlencode "some random" --data-urlencode "foo=bar" ""

# decode
url_decode ()
{
    : "${*//+/ }";
    echo -e "${_//%/\\x}"
}
```

## see also

- [[bash printf]]
- [[base64]]
- [[bash variables]]
- [[od]]
- [[ascii]]
- [[xxd]]
- [[tr]]
- [[fmt]]
- [how-to-urlencode-data-for-curl-command](https://stackoverflow.com/questions/296536/how-to-urlencode-data-for-curl-command)
