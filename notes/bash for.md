---
tags: [bash/keyword]
title: bash for
created: '2019-07-30T06:19:49.007Z'
modified: '2019-09-24T06:40:24.344Z'
---

# bash for

```sh
for name [in words]; do
  command $name;
done

f(){ for arg; do echo $arg; done }    # without `in` cycle thorugh positional arguments
```

#### set
```sh
set 1 2 3
for i do
  echo "$i"
done
```

#### range
> Bash v4.0+ has inbuilt support for setting up a step value using `{START..END..INCREMENT}` syntax:
```sh
for i in {0..10..2}; do 
     echo "Welcome $i times"
done
```

#### seq
```sh
for i in $(seq 1 2 20); do
   echo "Welcome $i times"
done
```

#### three-expression c-style

```sh
for (( EXP1; EXP2; EXP3 )); do
	command1
	..
done

for (( initialisation ; ending condition ; update )); do
  statements...
done

for (( c=1; c<=5; c++ )); do  
   echo "Welcome $c times"
done
```

#### infinite loop
```sh
for (( ; ; )); do
   echo "infinite loops [ hit CTRL+C to stop]"
done
```

#### break
```sh
for I in 1 2 3 4 5; do
  statements1     
  if (disaster-condition); then
	  break    	         # Abandon the loop.
  fi
  statements3          #While good and, no disaster-condition.
done
```

#### continue
```sh
for f in $FILES ; do
	if [ -f ${f}.bak ];	then      # if .bak backup file exists, read next file
		echo "Skiping $f file..."
		continue                    # read next file and skip the cp command
	fi
	cp $f $f.bak                  # make a backup
done
```

## see also
- [[bash arithmetic expansion]]
- [Bash "for" loop without a "in foo bar..." part - Unix & Linux Stack Exchange](https://unix.stackexchange.com/a/417296/193945)
