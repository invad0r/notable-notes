---
title: ffmpeg
created: '2021-03-10T11:11:18.975Z'
modified: '2022-02-09T16:24:31.670Z'
---

# ffmpeg

> video and audio converter 

## install

`brew install ffmpeg`

## usage

```sh
ffmpeg -i file.webp out.png   # convert webp to png

ffmpeg -i FILE.mov \ `# convert .mov to .gif`
  -filter_complex "[0:v] fps=12,scale=2048:-1,split [a][b];[a] palettegen [p];[b][p] paletteuse" \
  FILE.gif

ffmpeg -i FILE.mp3 -ss 00:00:00 -to 00:00:20 -c copy COPY.mp3   # crop audio file's first 20sek
```

## see also

- [[imagemagick]]
- [[youtube-dl]]
