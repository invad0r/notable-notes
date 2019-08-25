---
tags: [bash]
title: bash bats
created: '2019-07-30T06:19:49.026Z'
modified: '2019-08-25T20:06:40.962Z'
---

# bash bats


## debug bats output
```sh
@test 'test-a' {
  run bash -c 'echo ERROR; false'
  echo "status = ${status}"
  echo "output = ${output}"
  [ "$status" -eq 0 ]
}
```

### see also
- [govmomi/test_helper.bash at master · GitHub](https://github.com/vmware/govmomi/blob/master/govc/test/test_helper.bash)
