---
tags: [macos]
title: fmt
created: '2023-04-12T11:57:47.449Z'
modified: '2023-05-05T06:57:12.600Z'
---

# fmt

>  simple text formatter

## option

```sh
-c          # Center the text, line by line.  In this case, most of the other options are ignored; no splitting or joining of lines is done
-m          # Try to format mail header lines contained in the input sensibly
-n          # Format lines beginning with a ‘.’ (dot) character
-p          # Allow indented paragraphs.  Without the -p flag, any change in the amount of whitespace at the start of a line results in a new paragraph being begun
-s          # Collapse whitespace inside lines, so that multiple whitespace characters are turned into a single space.  (Or, at the end of a sentence, a double space.
-d chars    # Treat the chars (and no others) as sentence-ending characters.  By default the sentence-ending characters are full stop (‘.’), question mark (‘?’) and exclamation mark (‘!’)
-l number   # Replace multiple spaces with tabs at the start of each output line, if possible.  Each number spaces will be replaced with one tab.  The default is 8. If number is 0, spaces are preserved
-t number   # Assume that the input files' tabs assume number spaces per tab stop.  The default is 8
```

## usage

```sh
# Center the text in standard input
echo -e 'The merit of all things\nlies\nin their difficulty' | fmt -c


# Format the text in standard input collapsing spaces
echo -e 'Multiple   spaces    will be collapsed' | fmt -s
```

## see also

- [[go]]
- [[bash echo]]
