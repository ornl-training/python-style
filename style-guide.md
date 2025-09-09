---
title: Python Style Guide
teaching: 5 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

The [PEP 8 Style Guide for Python Code](https://peps.python.org/pep-0008/) gives coding conventions for code layout, comments, naming, and other programming recommendations. The [pep8.org](https://pep8.org/) website is another presentation of the style guide. By adhering to the Python style guide, developers can write consistent code that is readable and maintainable on small and large projects. Some of the major conventions suggested by the guide are demonstrated below but readers should review the PEP 8 guide for more information.

## Indentation

Use 4 spaces per indentation level and spaces are the preferred indentation method.

## Imports

Imports should be on separate lines except when using the from syntax. Imports are always put at the top of the file, just after any module comments and docstrings, and before module globals and constants.

```python
import os
import sys

from subprocess import Popen, PIPE
```

