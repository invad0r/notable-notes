---
title: xkcdpass
created: '2021-02-12T12:38:07.546Z'
modified: '2021-02-12T12:47:10.970Z'
---

# xkcdpass

> flexible and scriptable password generator which generates strong passphrases, inspired by [XKCD-936](http://xkcd.com/936/)

## install
`pip3 install xkcdpass`

## usage
```sh
# flags
#   -h, --help                                  show this help message and exit
#   -w WORDFILE, --wordfile=WORDFILE            list of valid words from which to generate passphrases
#   --min=MIN_LENGTH                            Minimum length of words to make password
#   --max=MAX_LENGTH                            Maximum length of words to make password
#   -n NUMWORDS, --numwords=NUMWORDS            Number of words to make password
#   -i, --interactive                           Interactively select a password
#   -v VALID_CHARS, --valid-chars=VALID_CHARS   valid chars, using regexp style (e.g. '[a-z]')
#   -V, --verbose                               report various metrics for given options, including word list entropy
#   -c COUNT, --count=COUNT                     number of passwords to generate
#   -d DELIM, --delimiter=DELIM                 separator character between words
#   -s SEP, --separator SEP                     separate generated passphrases with SEP.
#   -C CASE, --case CASE                        choose method for setting case of each word in passphras ['alternating', 'upper','lower', 'random', 'capitalize']
# ..


xkcdpass
correct horse battery staple

xkcdpass --count=5 --acrostic='chaos' --delimiter='-' --min=5 --max=6 --valid-chars='[a-z]'
```
## see also
- [[op]]
- [[mkpasswd]]
- [pypi.org/project/xkcdpass/](https://pypi.org/project/xkcdpass/)


