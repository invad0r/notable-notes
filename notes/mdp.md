---
title: mdp
created: '2022-04-05T09:09:21.947Z'
modified: '2022-04-06T07:38:45.745Z'
---

# mdp

> cli based markdown presentation tool

## install

```sh
brew install mdp
```

## flags

```sh
-d, --debug           # enable debug messages on STDERR, add it multiple times to increases debug level
-e, --expand          # enable character entity expansion
-f, --nofade          # disable color fading in 256 color mode
-h, --help            # display this help and exit
-i, --invert          # swap black and white color
-t, --notrans         # disable transparency in transparent terminal
-s, --noslidenum      # do not show slide number at the bottom
-v, --version         # display the version number and license
-x, --noslidemax      # show slide number, but not total number of slides
-c, --nocodebg        # don't change the background color of code blocks
```

## usage

```sh
mdp -ex FILE.md   # start presentation
```

## markdown

```sh
cat <<EOT > hello.md
%title: Presentation Title
%author: $(whoami)
%date: $(date)

-> # Slide 1 <-

Intro slide

---

-> ## Slide 2 <-

* Item 1
* Item 2
* Item 3

---
-> # Slide 3  <-

This one with a numbered list

1. Item 1
2. Item 2
3. Item 3

---

-> # Conclusion  <-

mdp supports *other* **formatting**, too. Give it a try!

EOT
```

## see also

- [[vim]]
- [[tmux]]
