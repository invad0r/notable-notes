---
tags: [tool]
title: youtube-dl
created: '2019-07-30T06:19:49.267Z'
modified: '2020-09-02T18:10:46.402Z'
---

# youtube-dl

## usage
```sh
youtube-dl --continue --extract-audio --audio-format mp3 h3Q12OkBTHk

# extract audio from playlist starting at playlist-index: 17
youtube-dl \
  --no-overwrites \
  --continue \
  --extract-audio \
  --audio-format mp3 \
  --playlist-start 17 \
  PLs0kY...1zFPzbn

youtube-dl --skip-download --write-thumbnail knGYTLTHV_E    # Download just the thumbnail from a youtube video.
```

## see also
- [[eyeD3]]
