---
title: localedef
created: '2020-03-03T07:15:49.031Z'
modified: '2020-03-03T07:19:55.937Z'
---

# localedef

>  define locale environment

## usage
```sh
# environment vairable
# LC_CTYPE          defines character classification and case conversion.
# LC_COLLATE        defines collation rules.
# LC_MONETARY       defines the format and symbols used in formatting of monetary information.
# LC_NUMERIC        defines the decimal delimiter, grouping, and grouping symbol for non-monetary numeric editing.
# LC_TIME           defines the format and content of date and time information.
# LC_MESSAGES       defines the format and values of affirmative and negative responses.

# environment variables that affect the execution of localedef
# LANG            Provide a default value for the internationalization variables that are unset or nullbehave as if none of the variables had been defined.
# LC_ALL          If set to a non-empty string value, override the values of all the other internationalization variables.
# LC_COLLATE      (This variable has no effect on localedef; the POSIX locale will be used for this category.)
# LC_CTYPE        Determine the locale for the interpretation of sequences of bytes of text data as characters (for example, single- as opposed to multi-byte characters in arguments and input files).  This variable has no effect on the processing of localedef input data; the POSIX locale is used for this purpose, regardless of the value of this variable.
# LC_MESSAGES     Determine the locale that should be used to affect the format and contents of diagnostic messages written to standard error.
# NLSPATH         Determine the location of message catalogues for the processing of LC_MESSAGES.

localedef -i en_US -f UTF-8 en_US.UTF-8
```
## see also
- [[locale]]
- [[bash]]
