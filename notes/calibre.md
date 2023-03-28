---
tags: [linux, macos]
title: calibre
created: '2021-02-25T16:55:40.941Z'
modified: '2023-03-25T12:25:33.854Z'
---

# calibre

## install

```sh
brew    install --cask calibre
apt-get install calibre
```

## usage

```sh
ebook-convert "book.epub" "book.mobi"

ebook-convert "book.azw3" "book.pdf"

for book in *.epub; do echo "converting: $book"; ebook-convert "$book" "$(basename "$book" .epub).mobi"; done
```

## see also

- [[markdown]]
- [[gc]]
