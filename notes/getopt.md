---
title: getopt
created: '2020-03-16T18:01:43.018Z'
modified: '2020-03-16T18:05:21.736Z'
---

# getopt
> parse option arguments - is not a bash builtin !

## usage
```sh
set -o errexit -o noclobber -o nounset -o pipefail
params="$(getopt -o ab:c -l alpha,bravo:,charlie --name "$0" -- "$@")"
#printf 'params: %q\n' $params
eval set -- "$params"
#printf '\nargs:%q\n' $*
while :; do
  case "$1" in
    -a|--alpha)
      echo alpha
      shift
      ;;
    -b|--bravo)
      echo "bravo=$2"
      shift 2
      ;;
    -c|--charlie)
      echo charlie
      shift
      ;;
    --)
      shift
      break
      ;;
    *)
      echo "Not implemented: $1" >&2
      exit 1
      ;;
  esac
done
```

## see also
- [[bash getopts]]
- [[bash while]]
- [[bash case]]
- [[bash eval]]
