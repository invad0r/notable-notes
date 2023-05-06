---
title: metaprogramming
created: '2023-05-06T14:15:38.796Z'
modified: '2023-05-06T14:19:21.971Z'
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

## see also

- [[rust]] `macros`
