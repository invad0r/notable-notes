---
title: imagemagick
created: '2020-12-28T21:19:42.860Z'
modified: '2020-12-28T21:24:11.953Z'
---

# imagemagick

> create, edit, compose, or convert bitmap images, can read and write images in a variety of formats

## usage
```sh
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
