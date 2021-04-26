---
title: imagemagick
created: '2020-12-28T21:19:42.860Z'
modified: '2021-04-14T14:18:21.663Z'
---

# imagemagick

> create, edit, compose, or convert bitmap images, can read and write images in a variety of formats

## install
`brew install imagemagick`

## usage
```sh
# generate pdf file
convert xc:none -page Letter  FILE.pdf
convert xc:none -page A4      FILE.pdf
convert xc:none -page 842x595 FILE.pdf

convert FILE.txt -page Letter FILE.pdf

# make an impact image
convert \
  -size 1000x600 \
  -define gradient:radii=1000,500 radial-gradient:#884b88-#010101 \
  -font Impact \
  -pointsize 72 \
  -fill white \
  -gravity center \
  -interline-spacing 50 \
  -annotate 0,0 "Now with more arguments!" now-with-more-arguments.png  
```

## see also
- [imagemagick.org](https://imagemagick.org/)
- [imagemagick.org/script/convert](https://imagemagick.org/script/convert.php)
- [[ffmpeg]]
- [[gs]] ghostscript
