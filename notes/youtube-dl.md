---
tags: [python]
title: youtube-dl
created: '2019-07-30T06:19:49.267Z'
modified: '2023-03-22T11:00:04.940Z'
---

# youtube-dl

> download videos from youtube.com or other video platforms

## install

```sh
```

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

youtube-dl `# extract audio from playlist starting at playlist-index: 17` \
  --no-overwrites \
  --continue \
  --extract-audio \
  --audio-format mp3 \
  --playlist-start 17 \
  PLs0kY...1zFPzbn

youtube-dl --skip-download --write-thumbnail knGYTLTHV_E    # Download just the thumbnail from a youtube video.
```

## see also

- [[imagemagick]]
- [[ffmpeg]]
- [[eyeD3]]
- [[python]]
