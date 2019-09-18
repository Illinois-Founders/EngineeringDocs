# Coding Standards

Coding standards are accepted by the team and reviewed regularly to ensure
consistency in our code base. Standards are a work in progress, and part of
the code review process should be ensuring compliance with the accepted standards.

## Python Standards

### PEP8

We follow [PEP8](https://www.python.org/dev/peps/pep-0008/), with specified choices where PEP8 is indifferent. Examples can be found in the original specification. At a high level, ensure code developed follows the following rules that we have highlighted:

- Function and variable names must be declared in `snake_case`, except `setUp` and `tearDown` in `unittest` test classes.
- Class names must be declared in `StudlyCaps`.
- 4 spaces per indentation level, no tabs.
- Imports should be on separate lines (incorrect: `import os, sys`).
- Absolute imports are preferred (`from mypkg import sibling` instead of `import mypkg` and calling `mypkg.sibling`).
- PEP8 is impartial to single or double quotes as long as they are consistent. Our Python projects use single quotes, except for docstrings (triple-quoted strings). Use double quotes when a string contains single or double quote characters to avoid backslashes (escaping) in the string.
- Comparisons to singletons (i.e. `None`) should always be done with `is` or `is not` rather than `==` or `!=`.

### Docstrings

We follow [PEP257](https://www.python.org/dev/peps/pep-0257/), with one specific addition. Examples can be found in the original specification. At a high level, ensure code developed includes docstrings that fit the following guidelines:

- All docstrings should be triple-quoted (`"""Example docstring"""`).
- For one-liner docstrings:
	- triple quotes should be on the same line as the opening quotes
	- no blank line before or after the docstring unless it is documenting a class
- Multi-line docstrings consists of a summary (one-line only) followed by a blank line, followed by a more detailed description.
- Although not specified in PEP257, we include a blank line after class definitions without doctrings to be consistent with those with docstrings.
