---
title: ffmpeg
created: '2021-03-10T11:11:18.975Z'
modified: '2021-03-11T08:00:31.802Z'
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
```
## see also
- [[imagemagick]]
