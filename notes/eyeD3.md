---
tags: [tool]
title: eyeD3
created: '2019-08-23T14:52:21.967Z'
modified: '2020-11-26T15:54:08.657Z'
---

# eyeD3

> tagging mp3

```sh
eyeD3 track01.mp3                     # list meta info

eyeD3 --artist "artist" track01.mp3   # add artist to meta

eyeD3 --add-image "$DIR/cover.jpg:FRONT_COVER" --artist "$ARTIST" --album "$ALBUM" \
  --title "${f##*-}" --track "${f%%-*}" "$DIR/${f}.mp3";
```

## see also
- [[youtube-dl]]
- [[python]]
