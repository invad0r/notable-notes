---
tags: [bash]
title: bash arguments
created: '2019-07-30T06:19:48.991Z'
modified: '2020-08-25T13:56:40.097Z'
---

# bash arguments

- `argument`   command is split into an array of strings named arguments; `$0`command-name
- `option`     documented type of argument modifying the behavior of a command; `-v` verbose
- `parameter`  argument that provides information to either the command or one  of its options e.g. in `-o file`, `file` is the parameter of the `-o` option 

## parsing flags
```sh
for i in "$@"; do
  case $i in
    -e=*|--extension=*)
      VERSION="${i#*=}"
      shift # past argument=value
      ;;
    -s=*|--searchpath=*)
      SEARCHPATH="${i#*=}"
      shift # past argument=value
      ;;
    -l=*|--lib=*)
      LIBPATH="${i#*=}"
      shift # past argument=value
      ;;
    --default)
      DEFAULT=YES
      shift # past argument with no value
      ;;
    *)
      # catch all
      ;;
  esac
done


CMD=(docker exec -it)
ARGS=()

for i in "$@"; do
  echo "i: $i"
  case $i in
      -e=*|--environment=*)
      # CMD="${i#*=}"
      echo "case i: ${i#*=}"
      CMD+=('-e '${i#*=})
      shift # past argument=value
      # shift
      ;;
      *)
      ARGS+=($i)
      ;;
  esac
  # shift
done

echo ${CMD[*]} ${ARGS[*]}
```

## see also
- [Difference between terms: "option", "argument", and "parameter"?](http://stackoverflow.com/questions/36495669/difference-between-terms-option-argument-and-parameter)
- [How do I parse command line arguments in Bash?](http://stackoverflow.com/questions/192249/how-do-i-parse-command-line-arguments-in-bash)
- [Passing named arguments to shell scripts](https://unix.stackexchange.com/a/204927)
- [What is the meaning of "${1#*-}"](https://stackoverflow.com/a/41806827)
- [Parameter expansion [Bash Hackers Wiki]](http://wiki.bash-hackers.org/syntax/pe#substring_removal)
- [[bash for]]
- [[bash case]]
- [[bash shift]]
