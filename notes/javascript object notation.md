---
tags: [javascript]
title: javascript object notation
created: '2023-05-24T11:44:11.052Z'
modified: '2023-05-24T14:14:53.137Z'
---

# javascript object notation

> `json`

## json grammar in McKeeman Form

```json
json
   element

value
   object
   array
   string
   number
   "true"
   "false"
   "null"

object
    '{' ws '}'
    '{' members '}'

members
    member
    member ',' members

member
    ws string ws ':' element

array
    '[' ws ']'
    '[' elements ']'

elements
    element
    element ',' elements

element
    ws value ws

string
'"' characters '"'

characters
    ""
    character characters

character
    '0020' . '10FFFF' - '"' - '\'
'\' escape

escape
    '"'
    '\'
    '/'
    'b'
    'f'
    'n'
    'r'
    't'
    'u' hex hex hex hex

hex
    digit
    'A' . 'F'
    'a' . 'f'

number
    integer fraction exponent

integer
    digit
    onenine digits
    '-' digit
    '-' onenine digits

digits
    digit
    digit digits

digit
    '0'
    onenine

onenine
    '1' . '9'

fraction
    ""
    '.' digits

exponent
    ""
    'E' sign digits
    'e' sign digits

sign
    ""
    '+'
    '-'

ws
    ""
    '0020' ws
    '000A' ws
    '000D' ws
    '0009' ws
```

[crockford.com/mckeeman](https://www.crockford.com/mckeeman.html)

## see also

- [[yaml]], [[jq]], [[yq]]
- [json.org/json-en](https://www.json.org/json-en.html)
- [crockford.com/mckeeman](https://www.crockford.com/mckeeman.html)
- [infoq.com/presentations/Heretical-Open-Source/](https://www.infoq.com/presentations/Heretical-Open-Source/)
