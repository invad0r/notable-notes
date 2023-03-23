---
title: ffmpeg
created: '2021-03-10T11:11:18.975Z'
modified: '2023-03-21T13:41:45.694Z'
---

# ffmpeg

> video and audio converter 

## install

```sh
brew install ffmpeg
```

## usage

```sh
ffmpeg -i FILE.mp3 -ss 00:00:00 -to 00:00:20 -c copy COPY.mp3   # crop audio file's first 20sek


ffmpeg -i FILE.webp FILE.png                                                                # convert .webp to .png
ffmpeg -i FILE.mov -vcodec h264 -acodec mp2 FILE.mp4                                        # convert .mov to .mp4
ffmpeg -i FILE.mov -c:v libvpx -crf 10 -b:v 1M -c:a libvorbis FILE.webm                     # convert .mov to .webm
ffmpeg -i FILE.mov -codec:v libtheora -qscale:v 7 -codec:a libvorbis -qscale:a 5 FILE.ogg   # convert .mov to .ogg

ffmpeg -i FILE.mov \ `# convert .mov to .gif`
  -filter_complex "[0:v] fps=12,scale=2048:-1,split [a][b];[a] palettegen [p];[b][p] paletteuse" FILE.gif
```

## see also

- [[ffplay]]
- [[imagemagick]]
- [[youtube-dl]]
