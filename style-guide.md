---
title: Python Style Guide
teaching: 5 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

The [PEP 8 Style Guide for Python Code](https://peps.python.org/pep-0008/) gives coding conventions for code layout, comments, naming, and other programming recommendations. The [pep8.org](https://pep8.org/) website is another presentation of the style guide. By adhering to the Python style guide, developers can write consistent code that is readable and maintainable on small and large projects. Some of the major conventions suggested by the guide are demonstrated below but readers should review the PEP 8 guide for more information.

## Indentation

Spaces (not tabs) are the preferred indentation method. Use 4 spaces per indentation level.

```python
# Correct

for x in range(10):
    print("x is", i)

def sayhello():
    x = "Hello there"
    return x

# Wrong

for x in range(10):
  print("x is", x)

def sayhello():
  x = "Hello there"
  return x
```

## Imports

Imports should be on separate lines except when using the from syntax. Imports are always put at the top of the file, just after any module comments and docstrings, and before module globals and constants.

```python
# Correct

import numpy
import polars

from subprocess import Popen, PIPE

# Wrong

import numpy, polars
```

Imports should be grouped in the order shown below. An empty line should be placed between each group of imports.

1. Standard library imports
2. Third party imports
3. Local application/library specific imports

```python
# Standard library

import os
import math

# Third party

import numpy as np
import matplotlib.pyplot as plt

# Local package

from mypackage.utils import sayhello
```

Wildcard imports such as `from package import *` should be avoided because it is unclear what is actually imported from the package. This confuses both human readers of the code as well as automated tools.

## Documentation strings

Documentation strings, or docstrings, should be written for modules, functions, classes, and methods to describe the associated code. Several docstring styles exist such as the [NumPy style](https://numpydoc.readthedocs.io/en/latest/format.html) and the [Google style](https://google.github.io/styleguide/pyguide.html#s3.8-comments-and-docstrings). The example below uses the Google docstring style.

```python
def sayhello(x: str) -> str:
    """Create a greeting to say hello to someone.

    Args:
        x: Name of a person for the greeting.

    Returns:
        A greeting for the given name.
    """
    greeting = f"Hello {x}, how are you today?"
    return greeting
```

## Naming conventions

Modules should have short lowercase names where underscores can be used to improve readability. Packages should also have short lowercase names but use of underscores is discouraged.

```bash
# Module names

downloader.py

file_downloader.py
```

```python
# Package names

import mypackage
```

Class names should use the capitalized words (or CapWords, CamelCase) convention.

```python
class Downloader:
    ...

dl = Downloader()

class FileDownloader:
    ...

file = FileDownloader()
```

Function and variable names should be lowercase with underscores to separate words for readability.

```python
def hello(x):
    return f"Hello {x}"

def say_hello(x):
    y = f"Hello {x}"
    print(y)
```

Constants are usually defined at the module level and written in all capital letters.

```python
# Contents of module named example.py

import numpy as np
import pandas as pd

TOTAL = 89

API_URL = "https://mywebsite/api:8090"
```
