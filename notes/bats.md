---
tags: [bash]
title: bats
created: '2019-07-30T06:19:49.026Z'
modified: '2020-03-12T14:07:29.945Z'
---

# bats

> `bats` is a `TAP-compliant` testing framework for bash, which provides a simple way to verify that the UNIX programs behave as expected

## usage
```sh
bats TEST.bats    # running tests

# variables
#  BATS_TEST_FILENAME        is the fully expanded path to the Bats test file.
#  BATS_TEST_DIRNAME         is the directory in which the Bats test file  # is located.
#  BATS_TEST_NAMES           is an array of function names for each test case.
#  BATS_TEST_NAME            is the name of the function containing the current test case.
#  BATS_TEST_DESCRIPTION     is the description of the current test case.
#  BATS_TEST_NUMBER          is the (1-based) index of the current test case in the test file.
#  BATS_TMPDIR               is the location to a directory that may be used to store temporary files.
```

## debug bats output
```sh
@test 'test-a' {
  run bash -c 'echo ERROR; false'
  echo "status = ${status}"
  echo "output = ${output}"
  [ "$status" -eq 0 ]
}
```

## see also
- https://github.com/sstephenson/bats
- [govmomi/test_helper.bash · GitHub](https://github.com/vmware/govmomi/blob/master/govc/test/test_helper.bash)
