# blktests-ci-conditions

This directory contains the condition files interpreted by run_ci script in the
blktests contrib directory.

## List file

The file "list" contains names of interpret target condition files. Each line of
the "list" should have one name of a conditionf ile. The name of the condition
file is used as the argument passed to the "check" script of the blktests. For
example, the condition file "block" indicates The command line "./check block".

## Condition file

Each condition file listed in the "list" file contains the lines to be placed in
the blktests config file. The file must have empty line at the end. When the
line has one of the following words, they are handled in special way.

### BLKTESTS_CI_CHECK_ARGS="X Y"

When the line has this keyword, "X Y" is passed to the "check" script of the
blktests. When this line does not exists, the name of the condition file is
passed to the "check" script.

### BLKTESTS_CI_TEST_DEVS="X Y"

When the line has this keyword, "X Y" is handled as shell variables. The
values of each element of "X Y" is referred to and set to TEST_DEVS=()
in the config file. This allows to specify test target devices of the
blktests CI test node.
