---
tags: [bash]
title: bats
created: '2019-07-30T06:19:49.026Z'
modified: '2020-03-16T17:35:16.830Z'
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

# needs space betweetn string and {
# closing } must be on new line
@test "Check that ls is available" {
    command -v ls
}

@test "Check the we have a /tmp directory" {
  run stat /tmp
  # standart bash test
  # $status and $output available
  echo $output
  [ $status = 0 ]
}

@test "Check that total is listed" {
  run ls -l
  echo ${lines[0]}
  [[ ${lines[0]} =~ "total" ]]
}


setup() {
  source "$BATS_TEST_DIRNAME/../bash_profile"
  script="$(basename $BATS_TEST_FILENAME)"
  script="${script%.*}"
}

@test "get usage: bluegreen-active" {
  script="$(basename $BATS_TEST_FILENAME)"
  script="${script%.*}"
  run "bluegreen-active -h"
#  echo "output: $output"
#  echo "status: $status"
#  echo ${lines[0]}
#  [ "$status" -eq 0 ]
  [ "${lines[0]}" = "usage: source $script.sh ENV" ]
}
```

## see also
- https://github.com/sstephenson/bats
- [govmomi/test_helper.bash · GitHub](https://github.com/vmware/govmomi/blob/master/govc/test/test_helper.bash)
- [engineyard.com/bats-test-command-line-tools](https://www.engineyard.com/blog/bats-test-command-line-tools)
