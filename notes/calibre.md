---
title: calibre
created: '2021-02-25T16:55:40.941Z'
modified: '2021-02-26T07:16:43.148Z'
---

# calibre

## install
`brew install --cask calibre`, `apt install calibre`

## usage
```sh
ebook-convert "book.epub" "book.mobi"

ebook-convert "book.azw3" "book.pdf"

for book in *.epub; do echo "converting: $book"; ebook-convert "$book" "$(basename "$book" .epub).mobi"; done
```
## see also
- 
