---
tags: [shell/bash/builtin]
title: bash break
created: '2019-08-02T06:42:37.559Z'
modified: '2021-05-12T08:46:07.583Z'
---

# bash break

> Exit for, while, or until loops.

## usage
```sh
break n   # If N is specified, break N enclosing loops


while [ 1 -eq 1 -a 1 -gt 0 ]; do
	echo "running.."; sleep 1;
	val=5
	until [ $val -eq 0 ]; do
		val=$((--val))
		rand=$(( ( RANDOM % 5) + 1 ))
		echo "[rand: $rand] reduced val to: $val.."; sleep 1;
		if [ $val -lt $rand ]; then
			break 2;
		fi
	done
done
```

## see also
- [[bash while]]
- [[bash for]]
- [[bash until]]
