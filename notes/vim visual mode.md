---
tags: [vim]
title: vim visual mode
created: '2019-07-31T06:11:23.688Z'
modified: '2020-04-23T09:49:18.961Z'
---

# vim visual mode

> visual mode permits the user to select the text using the keyboard

## usage
```vim
0
A     ; append end of line
a     ; append
D     ; delete
C     ; change

cw    ; correct word
dw    ; delete word

cW    ; correct whole word
dW    ; delete whole word




Ctl+b   ; page backward
Ctl+f   ; page forward

Ctl+d   ; 1/2 page down
Ctl+u   ; 1/2 page up

''      ; move prev curser position

gd             ; goto local declartion
gD             ; goto global declartion
g*             ; goto/jump to next occurrence under cursor
g#             ; goto/jump to prev occurrence under cursor
gt             ; goto next tab
gT             ; goto prev tab
[nnn] gt       ; goto numbered tab


; shares
md    ; marks share `d`
`d    ; navigate to exact position
'd    ; navigate to the line the holds definition

ggVGJ                 ; go to top of file, visually select to end of file and join lines

qqqqqJ@qq@q
; first three q's clear the `q` register
; qqJ@qq records a macro to the `q` register that performs a Join, then calls `q`
; the last `@q` runs it.

ctrl+v j j j j space space shift+i esc multiline-indent
; ctrl + v      then move up or down
; shift + i     multiline insert
; esc

c i w { Ctrl + r " }  wrap word in `{}`
; c i w         Delete the word the cursor is on, and end up in insert mode.
; {             add the first curly-brace
; ctrl + r"     Insert the contents of the `"` register, aka the last yank/delete
; }             add the closing curly-brace 

di'hPl2x  Unquote a word that's enclosed in single quotes
;   di'   Delete the word enclosed by single quotes
;   hP    Move the cursor left one place (on top of the opening quote) and put the just deleted text before the quote
;   l     Move the cursor right one place (on top of the opening quote)
;   2x    Delete the two quotes
```

```
$ cp monfichier.txt dir/a

```




![1215px-Vi-commands.svg.png](https://trmm.net/images/thumb/e/e0/Vi-commands.svg/1215px-Vi-commands.svg.png)
![1215px-Vi-commands.svg.png](https://pbs.twimg.com/media/EDwTWk_U0AEtegw?format=jpg&name=large)

## see also
- [[vim]]
- [[vim command mode]]
- [vim - Indent multiple lines quickly in vi - Stack Overflow](http://stackoverflow.com/a/235841/2087704)
- [Moving efficiently - Trammell Hudson's Projects](https://trmm.net/Moving_efficiently)


