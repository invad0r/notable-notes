---
tags: [Notebooks]
title: url encoding
created: '2019-08-21T09:32:17.675Z'
modified: '2023-03-23T10:20:37.931Z'
---

# url encoding

> urls can only be sent over the Internet using the ASCII character-set.

- urls often contain characters outside the `ascii` set and has to be converted into a valid `ascii` format
- url encoding replaces unsafe `ascii` characters with a `%` followed by two hexadecimal digits
- urls cannot contain spaces - encoding normally replaces a space with a `+` sign or with `%20`

## encode

```sh
echo -ne 'some random\nbytes' | xxd -plain | tr -d '\n' | sed 's/\(..\)/%\1/g'

curl -s -o /dev/null -w "%{url_effective}\n" --get --data-urlencode "some random" --data-urlencode "foo=bar" ""
```

## decode

```sh
url_decode ()
{
    : "${*//+/ }";
    echo -e "${_//%/\\x}"
}
```

## see also

- [[ascii]]
- [[xxd]]
- [[tr]]
- [how-to-urlencode-data-for-curl-command](https://stackoverflow.com/questions/296536/how-to-urlencode-data-for-curl-command)
