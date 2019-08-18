---
tags: [cli]
title: youtube-dl
created: '2019-07-30T06:19:49.267Z'
modified: '2019-07-30T08:29:46.851Z'
---

# youtube-dl


### extract audio from playlist starting at playlist-index: 17
```sh
youtube-dl \
  --no-overwrites \
  --continue \
  --extract-audio \
  --audio-format mp3 \
  --playlist-start 17 \
  PLs0kY...1zFPzbn
```
