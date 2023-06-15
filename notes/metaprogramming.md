---
tags: [Notebooks]
title: metaprogramming
created: '2023-05-06T14:15:38.796Z'
modified: '2023-05-24T08:42:21.302Z'
---

# metaprogramming

> technique in which programs threat themselves as data and can modify itself or other programs


## example

```sh
#!/bin/sh
# metaprogram
echo '#!/bin/sh' > program
for i in $(seq 992)
do
    echo "echo $i" >> program
done
chmod +x program
```

## reflection

> Reflection in computing is the ability of a program to examine its own structure, particularly through types; it’s a form of metaprogramming.

[go.dev/blog/laws-of-reflection](https://go.dev/blog/laws-of-reflection)

- gives ability to examine types at runtime
- allows to examine, modify, and create variables, functions, and structs at runtime

[medium.com/capital-one-tech/learning-to-use-go-reflection](https://medium.com/capital-one-tech/learning-to-use-go-reflection-822a0aed74b7)


[oracle.com/technical-resources/articles/java/javareflection.html](https://www.oracle.com/technical-resources/articles/java/javareflection.html)

## see also

- [[rust]] `macros`
- [[java]]
- [[go]]
