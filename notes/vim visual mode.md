---
tags: [vim]
title: vim visual mode
created: '2019-07-31T06:11:23.688Z'
modified: '2020-01-22T09:24:24.383Z'
---

# vim visual mode

> visual mode permits the user to select the text using the keyboard

## usage
<kbd>ggVGJ</kbd>  go to top of file, visually select to end of file and join lines

<kbd>qqqqqJ@qq@q</kbd>
- first three <kbd>q</kbd>'s clear the `q` register
- <kbd>qqJ@qq</kbd> records a macro to the `q` register that performs a Join, then calls `q`
- the last `@q` runs it.

<kbd>ctrl+v j j j j space space shift+i esc</kbd> multiline-indent
- <kbd>ctrl + v</kbd>  - then move up or down
- <kbd>shift + i</kbd>  - multiline insert
- <kbd>esc</kbd>

<kbd>c i w { Ctrl + r " }</kbd>  wrap word in `{}`
- <kbd>c i w</kbd> Delete the word the cursor is on, and end up in insert mode.
- `{` add the first curly-brace
- <kbd>ctrl + r"</kbd> - Insert the contents of the `"` register, aka the last yank/delete
- `}` add the closing curly-brace 

<kbd>di'hPl2x</kbd>  Unquote a word that's enclosed in single quotes
- <kbd>di'</kbd> Delete the word enclosed by single quotes.
- <kbd>hP</kbd> Move the cursor left one place (on top of the opening quote) and put the just deleted text before the quote.
- <kbd>l</kbd> Move the cursor right one place (on top of the opening quote).
- <kbd>2x</kbd> Delete the two quotes. 

## see also
- [[vim]]
- [[vim command mode]]
- [vim - Indent multiple lines quickly in vi - Stack Overflow](http://stackoverflow.com/a/235841/2087704)


