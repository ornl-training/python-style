---
title: Linting Python Code
teaching: 5 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

A code linter tool is a static code analysis program that automatically checks source code for errors, bugs, stylistic issues, and deviations from coding standards, all without executing the code. Linters help developers catch problems early by flagging questionable constructs, possible vulnerabilities, or code that doesn't follow best practices.

[Ruff](https://docs.astral.sh/ruff/) is a highly performant linter specifically for Python code. It checks for errors, style issues, and deviations from best practices, and can automatically fix some issues. It is a direct replacement for tools like Flake8, isort, pydocstyle, pyupgrade, and autoflake. Ruff is rapidly becoming the standard Python linting choice due to its speed, breadth of features, and ease of integration. Consequently, Ruff is used in this episode to demonstrate various linting features for Python code.

## Linting examples

Here is some poorly written Python code:

```Python
# bad_code.py

import os, sys   # multiple imports on one line

def add(x,y):    # missing whitespace after comma
    return x+ y  # inconsistent spacing

def unused_function():
    pass         # unused function

value = 42
print("The answer is: {}". format(value)) # space before format call
```

Next, run Ruff to check the code:

```bash
$ ruff check bad_code.py
```

Ruff will output the following errors and warnings about the code in the file:

```output
E401 [*] Multiple imports on one line
 --> bad_code.py:3:1
  |
1 | # bad_code.py
2 |
3 | import os, sys   # multiple imports on one line
  | ^^^^^^^^^^^^^^
4 |
5 | def add(x,y):    # missing whitespace after comma
  |
help: Split imports

F401 [*] `os` imported but unused
 --> bad_code.py:3:8
  |
1 | # bad_code.py
2 |
3 | import os, sys   # multiple imports on one line
  |        ^^
4 |
5 | def add(x,y):    # missing whitespace after comma
  |
help: Remove unused import

F401 [*] `sys` imported but unused
 --> bad_code.py:3:12
  |
1 | # bad_code.py
2 |
3 | import os, sys   # multiple imports on one line
  |            ^^^
4 |
5 | def add(x,y):    # missing whitespace after comma
  |
help: Remove unused import

Found 3 errors.
[*] 3 fixable with the `--fix` option.
```
