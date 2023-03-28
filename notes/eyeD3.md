---
tags: [linux, macos]
title: eyeD3
created: '2019-08-23T14:52:21.967Z'
modified: '2023-03-25T12:16:23.658Z'
---

# eyeD3

> tagging mp3

## install

```sh
brew install eye-d3
```

## usage

```sh
eyeD3 FILE.mp3                     # list meta info

eyeD3 --artist "artist" FILE.mp3   # add artist to meta

eyeD3 \
  --add-image "$DIR/cover.jpg:FRONT_COVER" \
  --artist "$ARTIST" \
  --album "$ALBUM" \
  --title "${f##*-}" \
  --track "${f%%-*}" \
  "$DIR/${f}.mp3"
```

## see also

- [[youtube-dl]]
- [[python]]
- [[ffmpeg]]
