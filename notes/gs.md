---
title: gs
created: '2021-04-14T13:59:38.784Z'
modified: '2022-01-26T15:42:43.830Z'
---

# gs

> ghostscript - postscript and pdf language interpreter and previewer

## install

`brew install ghostscript`

## usage

```sh
gs -dSAFER -dBATCH document.pdf                     # open in viewer

gs -sDEVICE=pdfwrite -o empty.pdf -c showpage       # generate empty pdf file

gs `# merge two pdfs into one` \
  -dNOPAUSE \
  -sDEVICE=pdfwrite \
  -sOUTPUTFILE=OUTPUTFILE.pdf \
  -dBATCH FILE_1.pdf FILE_2.pdf

# reduce pdf size
gs -dNOPAUSE -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook -dQUIET -sOutputFile=OUTPUTFILE.pdf -dBATCH big.pdf
# -dPDFSETTINGS=
#   /screen       screen-view-only quality, 72 dpi images
#   /ebook        low quality, 150 dpi images
#   /printer      high quality, 300 dpi images
#   /prepress     high quality, color preserving, 300 dpi imgs
#   /default      almost identical to /screen
```

## see also

- [ghostscript.com/doc/current/Devices](https://www.ghostscript.com/doc/current/Devices.htm)
- [tex.stackexchange.com/pdftex-reduce-pdf-size-reduce-image-quality](https://tex.stackexchange.com/a/41273)
- [[imagemagick]]
