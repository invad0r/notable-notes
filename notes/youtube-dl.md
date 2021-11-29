---
title: youtube-dl
created: '2019-07-30T06:19:49.267Z'
modified: '2021-10-31T14:56:47.640Z'
---

# youtube-dl

## usage
```sh
youtube-dl --continue --extract-audio --audio-format mp3 --embed-thumbnail h3Q12OkBTHk

youtube-dl --continue --extract-audio --audio-format mp3 --embed-thumbnail --batch-file FILE

youtube-dl \
  --extract-audio \
  -f bestaudio \
  -o '/PATH/FILE.mp3' \
  YOUTUBE_ID
  --metadata-from-title "%(artist)s - %(title)s" 2>&1

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
- [[python]]
